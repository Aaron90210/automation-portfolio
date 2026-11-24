# Weekly KPI Report Generator | n8n, Supabase, LLM, Slack

## 2. The Problem
Manually compiling weekly sales data and writing summary reports is time-consuming and prone to human error. This workflow automatically pulls data from a database, calculates the week-over-week performance, uses AI to write an encouraging commentary, and delivers the final report to the team.

## 3. Demo Video Link
[Paste your YouTube Unlisted link here]

## 4. Canvas Screenshot
![n8n Workflow Canvas](URL_TO_YOUR_SCREENSHOT_HERE)

## 5. How It Works
1. A Schedule Trigger runs every Friday at 5 PM.
2. n8n fetches all order data from a Supabase database.
3. A Code node calculates the Total Revenue, This Week's Revenue, and Last Week's Revenue.
4. An LLM reads the numbers and writes a short, professional commentary.
5. A second Code node formats the final report, ensuring the numbers are formatted correctly with commas and currency symbols (so the AI doesn't hallucinate the math).
6. The final report is sent via Email and posted to a Slack channel.

## 6. Tools & Credentials Needed
n8n (self-hosted via Docker), Supabase (PostgreSQL), Google Gemini (or OpenAI), Gmail API, Slack API.

## 7. Sample Input / Output
**Input (Raw SQL Data):**
```sql
select sum(amount) as total_revenue from orders;
-- Returns: 59316
