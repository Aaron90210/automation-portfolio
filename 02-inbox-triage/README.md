# AI Inbox Triage & Draft Assistant | n8n, LLM, Gmail, Slack

## 2. The Problem
Support teams get overwhelmed by repetitive emails and struggle to prioritize urgent issues. This workflow automates the initial triage, categorizes the email, and drafts a reply, ensuring urgent issues are flagged immediately.

## 3. Demo Video Link
[Paste your YouTube Unlisted link here]

## 4. Canvas Screenshot
![n8n Workflow Canvas](URL_TO_YOUR_SCREENSHOT_HERE)

## 5. How It Works
1. A new email arrives in the test inbox.
2. An LLM reads the email and categorizes it (Billing, Bug, How-To, Other).
3. The LLM drafts a polite, professional reply based on a strict policy.
4. Gmail creates a draft (never sends automatically) for human review.
5. The email details and AI response are logged to a Google Sheet.
6. If the urgency is "High," a Slack alert is sent to the team.
7. An Error Handler workflow catches any failures and alerts the team.

## 6. Tools & Credentials Needed
n8n (self-hosted via Docker), Google Gemini (or OpenAI), Gmail API, Google Sheets, Slack.

## 7. Sample Input / Output
**Input:**
An email from a customer: "I was charged twice this month. Refund me now."

**Output:**
```json
{
  "category": "Billing",
  "urgency": "High",
  "draft_reply": "Dear Customer, we apologize for the inconvenience. Our billing team will review this and get back to you within 24 hours."
}
