
Website RAG Assistant — Voice & Text AI Agent
An AI-powered website assistant built with n8n, Supabase Vector Store, OpenAI, and ElevenLabs. It allows website visitors to interact with the assistant through text chat or voice, ask questions about the website's knowledge base, and receive responses in the language they use.

Project: Saleha AI Studio — Website RAG Agent
Automation platform: n8n
Knowledge storage: Supabase Vector Store

Overview
This project combines Retrieval-Augmented Generation (RAG) with a website chat and voice interface. Instead of relying only on general AI knowledge, the assistant retrieves relevant information from a connected knowledge base before generating an answer.

Visitors can:

Ask questions through the website chat interface.
Talk to the assistant using the voice interface.
Communicate in their preferred language, including Bangla or English.
Receive answers grounded in the information available in the connected knowledge base.
The assistant is designed to respond in the language used by the visitor. Answer quality depends on the completeness and accuracy of the knowledge base.

Key Features
Text-based website chat for visitor questions.
Voice interaction through the embedded ElevenLabs conversational widget.
RAG-based answers using retrieved knowledge-base content.
Bangla and English interaction, with language-matched responses.
Supabase vector storage for indexed knowledge-base content.
n8n workflow orchestration for ingestion and question-answering.
Webhook-based communication between the website and n8n.
Conversation memory using the configured Postgres Chat Memory node.
Technology Stack
Technology / Node	Purpose
n8n	Workflow automation and orchestration
Google Drive Trigger	Detects new or updated knowledge-base files
Google Drive Download	Downloads source files
Extract from File	Extracts text from uploaded files
Code in JavaScript	Cleans and prepares extracted content
Default Data Loader	Prepares documents for vector indexing
OpenAI Embeddings	Converts text into vector embeddings
Supabase Vector Store	Stores and retrieves knowledge-base vectors
Webhook	Receives website chat requests
AI Agent	Coordinates question answering
OpenAI Chat Model	Generates conversational responses
Postgres Chat Memory	Maintains conversation context
Answer Questions with a Vector Store	Retrieves relevant knowledge for the AI Agent
Respond to Webhook	Sends the generated answer back to the website
ElevenLabs	Provides the website voice-conversation interface
Workflow Architecture
1. Knowledge-Base Ingestion Workflow
The ingestion workflow prepares documents and stores them in Supabase Vector Store.

Google Drive Trigger
        ↓
Google Drive Download
        ↓
Extract from File
        ↓
Code in JavaScript
        ↓
Default Data Loader
        ↓
OpenAI Embeddings
        ↓
Supabase Vector Store
Process:

A file is detected in the configured Google Drive location.
n8n downloads the file.
The Extract from File node extracts its text.
JavaScript prepares the extracted content.
The Data Loader structures the content as documents.
OpenAI Embeddings converts the content into vectors.
Supabase Vector Store stores the vectors for later retrieval.
2. Website Question-Answering Workflow
The second workflow handles questions submitted by website visitors.

Website Chat
     ↓
n8n Webhook
     ↓
AI Agent
  ├── OpenAI Chat Model
  ├── Postgres Chat Memory
  └── Answer Questions with a Vector Store
          └── Supabase Vector Store
                  └── OpenAI Embeddings
     ↓
Respond to Webhook
     ↓
Website Chat Response
Process:

The website sends a visitor's message to the n8n Webhook.
The AI Agent interprets the question.
The vector-store tool retrieves relevant knowledge-base information.
The configured chat model generates a response using the retrieved context.
Postgres Chat Memory provides conversation context.
Respond to Webhook returns the answer to the website.
3. Voice Interaction
The website also includes an embedded ElevenLabs conversational voice widget. Visitors can use the voice interface to speak with the assistant. The text chat and voice interface provide two ways to interact with the website assistant.

How to Use
Open the Saleha AI Studio website.
Use the chat widget to type a question, or open the voice interface to speak.
Ask about information covered by the connected knowledge base.
Continue the conversation with follow-up questions.
Setup Requirements
To recreate this project, you will need:

An n8n instance.
A Google account and Google Drive access.
A Supabase project with a configured vector store.
OpenAI API access for the configured chat and embedding nodes.
An ElevenLabs account and conversational widget configuration.
A website where the chat and voice interfaces can be embedded.
Configuration Notes
Configure credentials securely inside n8n; do not commit API keys, tokens, database passwords, or private webhook credentials to GitHub.
Configure the Supabase table, embedding model, vector dimensions, and metadata consistently with the n8n vector-store node.
Ensure the ingestion workflow runs successfully before testing knowledge-based answers.
Keep the website's allowed origins/CORS settings and webhook configuration aligned.
Test Bangla and English questions, follow-up questions, missing information, and unclear requests.
The assistant can only provide reliable knowledge-base answers when the source documents contain accurate and up-to-date information.
Important Limitations
The assistant cannot reliably answer questions that are not covered by its connected knowledge base.
Response quality depends on document quality, text extraction, chunking, embeddings, and retrieval configuration.
Voice availability and behavior depend on the ElevenLabs widget and its configuration.
This repository description documents the workflow shown in the project. Deployment credentials and private configuration are intentionally not included.
Privacy & Security
Never publish .env files, API keys, Supabase service-role keys, database passwords, or private webhook URLs.
Apply appropriate access controls and Row Level Security (RLS) policies in Supabase.
Restrict access to the n8n editor and credential store.
Only ingest documents that you are authorized to use.
Project Author
Saleha Akter
Founder — Saleha AI Studio
AI Automation Developer

License
Add a license file if you intend to distribute or reuse this project publicly. Until then, no reuse rights are granted by this README alone.

⋮⋮⋮⋮⋮⋮⋮⋮⋮⋮⋮⋮
