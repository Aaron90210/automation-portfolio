# AI Lead Qualifier & Router | n8n, LLM, Google Sheets, Slack

## 2. The Problem
Sales teams waste hours manually reading inbound forms to figure out who is a real buyer. This workflow automates the qualification process, ensuring hot leads are instantly routed to Slack while saving time on low-quality leads.

## 3. Demo Video Link
[Paste your YouTube Unlisted link here]

## 4. Canvas Screenshot
![n8n Workflow Canvas](URL_TO_YOUR_SCREENSHOT_HERE)

## 5. How It Works
1. The user fills out an n8n Form.
2. An LLM evaluates the lead's budget and message.
3. The LLM outputs strict JSON (Fit: High/Low, Reason, Next Step).
4. An IF node routes the lead based on the fit score.
5. High fit -> Slack alert + Google Sheet row.
6. Low fit -> Draft email + Google Sheet row.

## 6. Tools & Credentials Needed
n8n (self-hosted via Docker), Google Gemini (or OpenAI), Google Sheets API, Slack API, Gmail API.

## 7. Sample Input / Output
**Input:**
`{ "Name": "Jane Doe", "Budget": "5000", "Message": "I need this ASAP" }`

**Output:**
`{ "fit": "High", "reason": "Budget is above threshold.", "next_step": "Call immediately" }`

## 8. Test Results
[Write your results from Row 154 here, e.g., "Tested 20 leads, AI correctly categorized 18/20."]

## 9. Limitations & Improvements
Limitation: The AI occasionally hallucinates the JSON format if the prompt is too vague. 

Improvement: I will add a fallback error workflow to catch invalid JSON.
