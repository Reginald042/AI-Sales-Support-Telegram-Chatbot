# AI-Sales-Support-Telegram-Chatbot
An intelligent Telegram chatbot built with n8n that automates the customer journey from enquiry to order confirmation.
Instead of relying on static chatbot flows, the AI Agent understands customer intent, retrieves live information from a Supabase SQL database, maintains conversation context, processes orders, and notifies the sales team automatically., and sales team notifications.

## Overview
This project demonstrates how AI Agents can automate sales and customer support workflows for businesses.

When a customer sends a message through Telegram, the AI determines whether the customer needs:

-Product information

-Customer support

To place an order

The AI then calls the appropriate tool to complete the request before responding naturally.

If the customer decides to purchase, the chatbot collects the required information, creates the order automatically, and notifies the sales team via Gmail.

## Features

🤖 AI-powered Sales & Support Assistant

🛒 Product search using Supabase SQL

❓ FAQ retrieval using Supabase SQL

🧠 Conversation memory for contextual responses

📦 Automated order creation

📊 Order logging in supabase SQL

📧 Automatic Gmail notifications for the sales team

💬 Instant Telegram replies

🔀 Intelligent routing with n8n AI Agent and IF nodes

## Workflow

1. A customer sends a message to the Telegram chatbot.

2. The Telegram Trigger starts the workflow.

3. The AI Agent analyzes the customer's intent.

4. Based on the intent, the AI uses one or more of the following tools:
   - **Product Tool (Supabase SQL)** to retrieve product information such as price, availability, brand, and specifications.
   - **FAQ Tool (Supabase SQL)** to answer support questions such as delivery time, return policy, and other FAQs.

5. If the customer is only making an enquiry, the AI responds directly on Telegram, and the workflow ends.

6. If the customer wants to place an order, the AI naturally collects the required order details, including:
   - Customer Name
   - Phone Number
   - Email Address
   - Delivery Address
   - Product
   - Quantity

7. Once all required information has been collected, the AI calls the **Order Tool**, which creates a new order and appends it to the Orders supabase SQL.

8. The **IF Node** checks the AI Agent's output to determine whether an order was successfully created.

9. If an order was created (**True** branch):
   - The **Get Many Rows ** node retrieves the newly created order details.
   - The **Edit Fields** node maps and formats the order information.
   - The **Gmail** node sends a structured order notification to the sales team for immediate follow-up.
   - The **Telegram** node sends an order confirmation message back to the customer.

10. If no order was created (**False** branch):
    - The workflow skips the sales notification process.
    - The AI's response is sent directly to the customer on Telegram.
  
## Tech Stack

n8n

Groqchat model

Telegram Bot API

Supabase SQL


Gmail

Simple Memory

## Skills Demonstrated

AI Agents

Workflow Automation

Prompt Engineering

Tool Calling

SQL Database Integration

API Integration

Business Process Automation

n8n
Supabase

Groq

Telegram Bot Development

## License

MIT License

