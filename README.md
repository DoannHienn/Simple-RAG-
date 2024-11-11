# Simple-RAG
**Simple-RAG**

Let's create a simple RAG system that retrieves information from a predefined dataset and generates responses based on the retrieved knowledge. The system will comprise the following components:

<img src="https://huggingface.co/ngxson/demo_simple_rag_py/resolve/main/diagram_2_mermaid-423723682-light-mermaid.svg" alt="image" width="500" />




Embedding model: A pre-trained language model that converts input text into embeddings - vector representations that capture semantic meaning. These vectors will be used to search for relevant information in the dataset.

Vector database: A storage system for knowledge and its corresponding embedding vectors. While there are many vector database technologies like Qdrant, Pinecone, and pgvector, we'll implement a simple in-memory database from scratch.

Chatbot: A language model that generates responses based on retrieved knowledge. This can be any language model, such as Llama, Gemma, or GPT.




**Example**

In this example, we will write a simple Python implement of RAG.

To run the models, we will use ollama, a command line tool that allows you to run models from Hugging Face. With ollama, you don't need to have access to a server or cloud service to run the models. You can run the models directly on your computer.

For the models, let's use the following:


Embedding model: hf.co/CompendiumLabs/bge-base-en-v1.5-gguf

Language model: hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF

And for the dataset, we will use a simple list of facts about cat. Each fact will be considered as a chunk in the indexing phrase.
