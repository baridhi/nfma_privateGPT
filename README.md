# NFMA Private GPT
Create a private GPT for the National Federation of Municipal Analysts (NFMA).


This project aims to create a private version of a GPT to chat with PDF documents.
Specifically, municipal bond offering statements were used. First, I create an initial embedding of the document using ingest/ingest.py.
Thereafter, I create an app to choose different large language models (LLM) which allow interacting with the PDF. 
These LLMs are available to me locally on my computer using Ollama (and do not use API or web interaction). 
However, the user-interface of the app is hosted on a browser but does not use the internet. 

I've tinkered with different AI models ranging from Llama to Deepseek, but found the Mistral AI model performing the best. 
So, it is set as default for now. Of course, these upstream models are not trained for muni bonds. That would be the gold standard and I would need GPUs. 
My current approach uses retrieval augmented generation (RAG) on top of open-source LLM's.

# Ollama Set up
See the instructions here: https://github.com/ollama/ollama


# Steps

In order to run this repository, do the following:

1. Navigate to the sub-folder where you store/clone this code.

2. Create a virtual python environment (on Mac bash):
   python3 -m venv pvenv

3. Activate the virtual environment as below:
   source pvenv/bin/activate

4. Set up the packages required for this project:
   pip3 install -r requirements_pinned.txt

5. Run the script to vectorize the document:
   python3 ./ingest/ingest.py
   
6. Launch the user-interface app by running:
   streamlit run ./assistant/assistant_ui.py




