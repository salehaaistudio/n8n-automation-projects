# 🤖 Shopify AI Automation Agent

An AI-powered Shopify store management assistant built with **n8n, Google Gemini, Telegram Bot API, and Shopify**.

This project allows store administrators to manage their Shopify store through natural-language messages in Telegram. The AI Agent understands user requests, selects the appropriate Shopify tools, performs the requested operations, and sends automated responses through Telegram.

---

## 🚀 Project Overview

Managing an e-commerce store involves repetitive tasks such as checking products, reviewing orders, creating products, updating product information, and deleting products.

This project simplifies these operations through an AI-powered Telegram assistant. Users can communicate with the bot using everyday language instead of manually navigating the Shopify dashboard for every supported task.

## ✨ Key Features

- 🛍️ **Get All Products:** Retrieve product information from Shopify.
- 📦 **Get All Orders:** Retrieve order information from the connected store.
- ➕ **Create Products:** Create new products using user-provided details.
- ✏️ **Update Products:** Update existing product information.
- 🗑️ **Delete Products:** Delete products through Shopify integration.
- 🧠 **Natural Language Understanding:** Interpret conversational instructions using Google Gemini.
- 💬 **Telegram Integration:** Send requests and receive automated responses through Telegram.
- 🧠 **Conversation Memory:** Maintain conversational context using n8n Simple Memory.
- 📣 **AI Product Assistance:** Generate product summaries, use cases, and marketing highlights for new products.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Google Gemini | AI language model |
| Telegram Bot API | User interaction and messaging |
| Shopify API | Product and order management |
| AI Agent | Understands requests and selects appropriate tools |
| Simple Memory | Maintains conversation context |

## 🔄 Workflow Architecture

The automation follows this structure:

```text
                 Telegram User
                       |
                       v
                Telegram Trigger
                       |
                       v
                    AI Agent
                       |
          +------------+------------+
          |            |            |
          v            v            v
     Gemini Chat    Simple       Shopify
       Model        Memory        Tools
                                    |
                 +------------------+------------------+
                 |          |         |        |       |
                 v          v         v        v       v
             Get All    Get All    Create   Update   Delete
             Products   Orders    Product  Product  Product
                 |          |         |        |       |
                 +----------+---------+--------+-------+
                                    |
                                    v
                           Telegram Response
```

## ⚙️ How It Works

### 1. Telegram User Interaction

The user sends a natural-language message to the Telegram bot.

Example requests:

- Show all my products.
- Get my Shopify orders.
- Create a new product.
- Update an existing product.
- Delete a product.

### 2. AI Request Processing

The Telegram Trigger receives the message and forwards it to the n8n AI Agent.

Google Gemini interprets the user's request and helps determine which connected Shopify tool should be used.

### 3. Shopify Operations

The AI Agent connects to the configured Shopify tools to perform the requested operations:

- Retrieve all products.
- Retrieve order information.
- Create new products.
- Update existing products.
- Delete products.

### 4. Automated Telegram Response

After processing the request, the workflow sends the result or response back to the user through Telegram.

### 5. Conversation Memory

The n8n Simple Memory component maintains conversational context and supports follow-up interactions.

## 💬 Example Interaction

**User:** Show my Shopify products.

**AI Assistant:** Retrieves and returns product information from the connected Shopify store.

**User:** Create a new product.

**AI Assistant:** Requests the necessary product details, such as title, description, and product type.

**User:** Update an existing product.

**AI Assistant:** Processes the update request using the connected Shopify tool.

## 📸 Project Screenshots

### 1. Shopify Store Dashboard

Shows the Shopify storefront and administration interface.

### 2. Telegram AI Assistant

Demonstrates natural-language communication and automated Shopify management responses.

### 3. n8n Automation Workflow

Shows the complete workflow, including Telegram Trigger, AI Agent, Google Gemini, Simple Memory, and Shopify tools.

## 🔧 Setup Requirements

To recreate this project, you need:

- An n8n instance.
- A Shopify development store or authorized Shopify store.
- Shopify API credentials with the required permissions.
- A Telegram bot and Bot Token.
- Google Gemini API access and credentials.
- Configured n8n Telegram, Shopify, and Gemini nodes.

## ⚙️ Configuration Guide

1. Set up your Telegram bot and configure its credentials in n8n.
2. Configure Google Gemini Chat Model credentials.
3. Connect the Gemini model to the AI Agent.
4. Configure Simple Memory for conversational context.
5. Connect Shopify credentials with the required API permissions.
6. Add the Shopify product and order tools to the AI Agent.
7. Configure the Telegram Trigger to receive messages.
8. Configure the Telegram Send Message node to return responses.
9. Test all operations using an authorized Shopify test store.

## 🔐 Security Considerations

- Never publish API keys, Telegram bot tokens, Shopify access tokens, or passwords.
- Store credentials securely using n8n credential management.
- Grant only the Shopify permissions required by the workflow.
- Protect access to the n8n instance and credential store.
- Test destructive operations, such as product deletion, carefully.
- Use an authorized Shopify store for all testing.

## 🧪 Testing & Project Status

The project owner reports that all workflow nodes and connected operations have been tested successfully.

The workflow integrates product retrieval, order retrieval, product creation, product updates, and product deletion with Telegram-based AI interaction.

## 🎯 Project Outcome

Built an AI-powered conversational Shopify management system that combines n8n workflow automation, Google Gemini, Telegram, and Shopify integration.

The system simplifies essential e-commerce management operations by allowing store administrators to interact with their Shopify store through natural-language messages.

## 👩‍💻 Project Author

**Saleha Akter**  
Founder — **Saleha AI Studio**  
AI Automation Developer

## 📄 License

No open-source license has been specified for this repository. All rights reserved unless a license is added.
