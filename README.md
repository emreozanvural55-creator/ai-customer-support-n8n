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
