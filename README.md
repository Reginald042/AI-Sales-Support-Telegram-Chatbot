# AI-Sales-Support-Telegram-Chatbot
An intelligent Telegram chatbot built with n8n that automates the customer journey from enquiry to order confirmation.
Instead of relying on static chatbot flows, the AI Agent understands customer intent, retrieves live information from a Supabase SQL database, maintains conversation context, processes orders, and notifies the sales team automatically., and sales team notifications.

## Overview
This project demonstrates how AI Agents can automate sales and customer support workflows for businesses.
When a customer sends a message through Telegram, the AI determines whether the customer needs:
Product information
Customer support
To place an order
The AI then calls the appropriate tool to complete the request before responding naturally.
If the customer decides to purchase, the chatbot collects the required information, creates the order automatically, and notifies the sales team via Gmail.

## Features
🤖 AI-powered Sales & Support Assistant
🛒 Product search using Supabase SQL
❓ FAQ retrieval using Supabase SQL
🧠 Conversation memory for contextual responses
📦 Automated order creation
📊 Order logging in Google Sheets
📧 Automatic Gmail notifications for the sales team
💬 Instant Telegram replies
🔀 Intelligent routing with n8n AI Agent and IF nodes

## Workflow
1.Customer sends a message through Telegram.
2.Telegram Trigger starts the workflow.
3.AI Agent determines the customer's intent.
4.The AI queries either:
 -Product Tool (Supabase SQL)
 -FAQ Tool (Supabase SQL)
 -Order Tool (Google Sheets) when an order is confirmed.
5.IF Node evaluates the AI Agent's output.
6.If the request is an enquiry:
 -The workflow follows the False branch.
 -The chatbot replies directly to the customer on Telegram.
7.If the request is an order:
 -The workflow follows the True branch.
 -Retrieves the newly created order from Google Sheets.
 -Maps the order details.
 -Sends a Gmail notification to the sales team.
 -Sends an order confirmation to the customer on Telegram.
 
## Tech Stack
n8n
Groq chat model
Telegram Bot API
Supabase SQL
Google Sheets
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

