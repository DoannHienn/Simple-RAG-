# Simple-RAG-
In this example, we will write a simple Python implement of RAG.

To run the models, we will use ollama, a command line tool that allows you to run models from Hugging Face. With ollama, you don't need to have access to a server or cloud service to run the models. You can run the models directly on your computer.

For the models, let's use the following:


Embedding model: hf.co/CompendiumLabs/bge-base-en-v1.5-gguf

Language model: hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF
And for the dataset, we will use a simple list of facts about cat. Each fact will be considered as a chunk in the indexing phrase.
