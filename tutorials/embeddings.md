An **embedding model** is a type of machine learning model that converts high-dimensional data (such as words, sentences, images, or user interactions) into low-dimensional **vector representations** while preserving meaningful relationships in the data. These vector representations, called **embeddings**, capture semantic similarities between different entities.

### Common Types of Embedding Models:
1. **Word Embeddings (NLP)**
   - **Word2Vec**: Generates word vectors using **CBOW** or **Skip-gram**.
   - **GloVe**: Constructs embeddings based on word co-occurrence.
   - **FastText**: Extends Word2Vec by considering subword information.
   - **Transformer-based Models**: BERT, GPT, and other deep learning models generate context-aware embeddings.

2. **Sentence & Document Embeddings**
   - **TF-IDF, LSA, LDA**: Older techniques for representing documents.
   - **BERT, SBERT**: Deep learning models that create context-rich sentence embeddings.

3. **Graph Embeddings**
   - **Node2Vec, DeepWalk**: Learn node embeddings in graphs.
   - **Graph Neural Networks (GNNs)**: Generate graph-aware embeddings.

4. **Image Embeddings**
   - **CNN-based models** (ResNet, VGG, EfficientNet) extract feature embeddings from images.
   - **CLIP**: Aligns image and text embeddings.

5. **Recommendation Systems**
   - **Collaborative filtering embeddings**: Represent users and items in a shared space.
   - **Neural Collaborative Filtering (NCF)**: Learns user-item interaction embeddings.

6. **Multimodal Embeddings**
   - Combine different data types (e.g., text, images, audio) into a shared vector space (e.g., CLIP, Flamingo).

### Applications:
✅ **Natural Language Processing (NLP)** – Sentiment analysis, machine translation, chatbot responses  
✅ **Computer Vision** – Image retrieval, object detection, facial recognition  
✅ **Recommendation Systems** – Personalized recommendations based on user preferences  
✅ **Search & Information Retrieval** – Semantic search, keyword expansion  
✅ **Graph Analysis** – Social network analysis, fraud detection  

