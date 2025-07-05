# AI-Powered Financial Chart Analysis Backend

This workflow serves as the backend for a browser extension designed to provide AI-powered technical analysis of financial charts. It receives a chart image (e.g., from TradingView) via a webhook, analyzes it using OpenAI's `gpt-4o-mini` vision model, and returns a simplified analysis suitable for novice traders.

## Overview

The goal of this project is to make technical chart analysis more accessible. A user with a Chrome extension can capture a screenshot of a financial chart. The extension sends this image to the n8n webhook, which then uses a powerful AI model to interpret the chart. [cite_start]The analysis is then sent back to the user, explaining potential market movements in simple language. [cite: 145, 147]

## Features

* [cite_start]**Webhook Trigger:** Listens for POST requests from a client, such as a Chrome extension, containing image data[cite: 144].
* **AI Vision Analysis:** Utilizes the `gpt-4o-mini` model from OpenAI to analyze the provided chart image.
* [cite_start]**Expert Prompting:** The AI is prompted to act as an expert financial analyst, focusing on technical indicators and providing simple insights[cite: 145, 146].
* [cite_start]**User-Friendly Response:** The analysis is formulated in "infant language" to be easily understood by beginners, and includes a disclaimer that it is not binding financial advice[cite: 145, 148].
* **Direct Response:** The `Respond to Webhook` node sends the generated analysis directly back to the calling client.

## How It Works

1.  A user captures a financial chart image using a browser extension.
2.  The extension sends the image data (as Base64) in a POST request to the n8n `Webhook` node.
3.  The `OpenAI` node receives the image data and sends it to the `gpt-4o-mini` vision model with a specialized prompt.
4.  The AI analyzes the chart and generates a text-based technical analysis.
5.  The `Respond to Webhook` node takes the AI-generated text and sends it back as the response to the initial request from the browser extension.

## Technologies Used

* n8n
* OpenAI (`gpt-4o-mini` with vision capabilities)

## Setup & Configuration

1.  **OpenAI Credentials:** Add your OpenAI API key to the `OpenAI` node in the n8n workflow.
2.  **Webhook URL:** Once the workflow is active, the Webhook URL will be generated. You will need to use this URL in your Chrome extension's code to send the POST requests.
3.  **Chrome Extension:** You need to build a simple Chrome extension that can capture a screenshot and send it as a Base64-encoded string in the body of a POST request to the n8n webhook URL.

## How to Use

1.  Activate the n8n workflow.
2.  Use your custom-built Chrome extension to send a chart image to the webhook URL.
3.  The extension will receive the AI-generated analysis as a text response.

[Book a chat with me😁](https://cal.com/closegem/coffee-chat)
