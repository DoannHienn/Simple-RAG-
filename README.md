# Simple-RAG-
In this example, we will write a simple Python implement of RAG.

To run the models, we will use ollama, a command line tool that allows you to run models from Hugging Face. With ollama, you don't need to have access to a server or cloud service to run the models. You can run the models directly on your computer.

For the models, let's use the following:


Embedding model: hf.co/CompendiumLabs/bge-base-en-v1.5-gguf

Language model: hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF

And for the dataset, we will use a simple list of facts about cat. Each fact will be considered as a chunk in the indexing phrase.
Simple RAG
Let's create a simple RAG system that retrieves information from a predefined dataset and generates responses based on the retrieved knowledge. The system will comprise the following components:


Embedding model: A pre-trained language model that converts input text into embeddings - vector representations that capture semantic meaning. These vectors will be used to search for relevant information in the dataset.
Vector database: A storage system for knowledge and its corresponding embedding vectors. While there are many vector database technologies like Qdrant, Pinecone, and pgvector, we'll implement a simple in-memory database from scratch.
Chatbot: A language model that generates responses based on retrieved knowledge. This can be any language model, such as Llama, Gemma, or GPT.
Indexing phase
The indexing phase is the first step in creating a RAG system. It involves breaking the dataset (or documents) into small chunks and calculating a vector representation for each chunk that can be efficiently searched during generation.


The size of each chunk can vary depending on the dataset and the application. For example, in a document retrieval system, each chunk can be a paragraph or a sentence. In a dialogue system, each chunk can be a conversation turn.

After the indexing phrase, each chunk with its corresponding embedding vector will be stored in the vector database. Here is an example of how the vector database might look like after indexing:

Chunk	Embedding Vector
Italy and France produce over 40% of all wine in the world.	
0.1,0.04,−0.34,0.21,...
The Taj Mahal in India is made entirely out of marble.	
−0.12,0.03,0.9,−0.1,...
90% of the world's fresh water is in Antarctica.	
−0.02,0.6,−0.54,0.03,...
...	...
The embedding vectors can be later used to retrieve relevant information based on a given query. Think of it as SQL WHERE clause, but instead of querying by exact text matching, we can now query a set of chunks based on their vector representations.

To compare the similarity between two vectors, we can use cosine similarity, Euclidean distance, or other distance metrics. In this example, we will use cosine similarity. Here is the formula for cosine similarity between two vectors A and B:



Don't worry if you are not familiar with the formula above, we will implement it in the next section.
