# Indexing in LlamaIndex

## Overview
With your data loaded, you now have a list of `Document` objects (or a list of `Node` objects). The next step is to build an **Index** over these objects so that you can query them efficiently using a Large Language Model (LLM).

## What is an Index?
In **LlamaIndex**, an **Index** is a data structure composed of `Document` objects, designed to enable querying by an LLM. The type of Index you choose should complement your querying strategy.

LlamaIndex provides several different index types, with the two most common being:

- **Vector Store Index**
- **Summary Index**

## Vector Store Index
A **Vector Store Index** is the most frequently used index type. It processes your documents by:

1. Splitting them into **Nodes**.
2. Generating **vector embeddings** for the text in each node.
3. Storing these embeddings to enable efficient semantic search.

### What is an Embedding?
A **vector embedding** is a numerical representation of the meaning (semantics) of text. Texts with similar meanings will have mathematically similar embeddings, even if their wording is different.

Embeddings enable **semantic search**, allowing LlamaIndex to retrieve information based on meaning rather than exact keyword matches. This is a key aspect of **Retrieval-Augmented Generation (RAG)** and how LLMs process queries.

### Embeddings in LlamaIndex
LlamaIndex uses OpenAI’s `text-embedding-ada-002` by default. However, depending on the LLM you are using, you may want to choose different embeddings for better efficiency and accuracy.

### How Vector Store Index Works
1. **Embeds your documents**: Converts text into vector embeddings using an API.
2. **Processes queries**: When a query is made, it is also converted into an embedding.
3. **Performs similarity search**: The query embedding is compared to stored embeddings to find the most semantically similar ones.

### Top-K Retrieval
The **top_k** parameter determines how many of the most relevant embeddings are retrieved in response to a query. This process is known as **top-k semantic retrieval**.

## Using Vector Store Index
To create a **Vector Store Index**, pass the list of `Document` objects you created:

```python
from llama_index.core import VectorStoreIndex

index = VectorStoreIndex.from_documents(documents)
```

### Tip
You can enable a progress bar during index construction by setting `show_progress=True`:

```python
index = VectorStoreIndex.from_documents(documents, show_progress=True)
```

Alternatively, you can build an index directly from a list of `Node` objects:

```python
index = VectorStoreIndex(nodes)
```

## Summary Index
A **Summary Index** is a simpler type of index. Instead of embedding text, it stores all `Document` objects and returns them when queried. This index type is best suited for queries that require summarizing a dataset rather than retrieving specific semantic matches.

## Further Reading
If your data consists of interconnected concepts (a **graph structure** in computer science terms), consider using the **Knowledge Graph Index** for better querying and retrieval.

---
Now that your text is indexed, it is technically ready for querying! However, embedding large amounts of text can be **time-consuming** and **expensive** when using a hosted LLM. To optimize costs and performance, consider **storing your embeddings** for reuse.

Happy indexing with **LlamaIndex**! 🚀
