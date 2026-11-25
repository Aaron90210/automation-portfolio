# Knowledge-Base Support Agent | n8n, Supabase, RAG, LLM

## 2. The Problem
Support teams waste hours answering the same repetitive questions, and AI chatbots often hallucinate answers to questions they don't know. This workflow uses Retrieval-Augmented Generation (RAG) to answer questions based ONLY on the company's private FAQ data, and safely escalates unknown questions to a human.

## 3. Demo Video Link
[Paste your YouTube Unlisted link here]

## 4. Canvas Screenshot
![n8n Workflow Canvas](URL_TO_YOUR_SCREENSHOT_HERE)

## 5. How It Works
1. A user sends a message via the Chat Trigger.
2. The AI Agent (with memory) receives the message.
3. The Agent uses the Supabase Vector Store tool to search the company's FAQ database for a semantic match.
4. If a match is found, the LLM generates a polite reply based ONLY on that retrieved data.
5. If no match is found, the Agent uses the "Log Escalation" tool to write the question to a Google Sheet and alerts the human team.

## 6. Tools & Credentials Needed
n8n (self-hosted via Docker), Google Gemini (LLM & Embeddings), Supabase (Vector Database), Google Sheets.

## 7. Sample Input / Output
**Input:** "Do you offer a free trial?"
**Output:** "Yes, all new users get a 14-day free trial of the Pro Plan. No credit card is required to start."

**Input:** "What is your CEO's name?"
**Output:** "I don't have that information right now. Let me escalate this to a human agent." *(Logs question to Google Sheet)*

## 8. Test Results
I tested the agent with 10 questions (5 from the FAQ, 5 outside). The RAG system successfully answered 100% of the in-scope questions without hallucinating. It correctly identified the 5 out-of-scope questions and escalated them to the Google Sheet.

## 9. Limitations & Improvements
**Limitation:** The chat memory is limited to the current session. 
**Improvement:** In the future, I would connect this to a persistent database (like Redis) so the bot remembers users across different days.
