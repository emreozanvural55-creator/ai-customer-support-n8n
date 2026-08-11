# AI Customer Support Automation with n8n

An AI-powered customer support automation workflow built with n8n.

## Features

- Receives customer support requests through Webhook
- Extracts customer information
- Uses Google Gemini to analyze support requests
- Automatically classifies:
  - Category
  - Priority
  - Sentiment
  - Human escalation requirement
  - Issue summary
- Stores support tickets in Supabase
- Sends escalation emails through Gmail

## Workflow

Webhook
↓
Edit Fields
↓
Google Gemini Information Extractor
↓
Supabase
↓
IF Human Required
↓
Gmail Notification

## Technologies

- n8n
- Google Gemini
- Supabase
- Gmail API
- Webhooks

## Example

Customer message:

> My product has not arrived for five days and I am very angry.

AI output:

```json
{
  "category": "shipping",
  "priority": "high",
  "sentiment": "negative",
  "requires_human": true,
  "summary": "The customer is very angry because their product has not arrived for five days."
}


## How It Works

The workflow receives customer support requests through a webhook and processes them using Google Gemini.

### 1. Webhook
Receives customer information:

- Name
- Email
- Message

### 2. Information Extraction

Google Gemini analyzes the customer's message and extracts structured information:

- Category
- Priority
- Sentiment
- Human support requirement
- Summary

### 3. Supabase

The analyzed support ticket is automatically stored in a Supabase database.

### 4. Human Escalation

The workflow checks whether human support is required.

If `requires_human` is `true`, an automatic email notification is sent to the support team through Gmail.

If `requires_human` is `false`, no escalation email is sent.

## Example Workflow

```text
Customer Request
       ↓
    Webhook
       ↓
  Edit Fields
       ↓
Google Gemini AI
       ↓
 Supabase Database
       ↓
  Human Required?
     ↙       ↘
   YES        NO
    ↓          ↓
  Gmail      End
