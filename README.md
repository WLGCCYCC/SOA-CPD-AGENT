# ⚖️ CPD Agent — CIA & SOA Continuing Professional Development Tracker

**Built by Shawn Yu, FSA — for actuaries, by an actuary.**

Tired of manually tracking your CPD hours? This AI-powered agent helps you log activities, track your progress toward CIA and SOA requirements, and find free guided CPD — all in one place.

> 🇨🇦 Designed for Canadian actuaries who are dual members of the **CIA** and **SOA**. Meeting the CIA requirement automatically satisfies the SOA requirement.

---

## What It Does

- 📊 **Live dashboard** — see your total, guided, and self-study hours at a glance
- 🧘 **Professionalism tracking** — know if you've met the mandatory professionalism requirement
- 📅 **Pace tracking** — see how your hours are spread across the rolling 2-year window
- 🤖 **AI chat agent** — describe what you did and it logs it for you
- 🎤 **Voice input** — speak your activity instead of typing
- 📸 **Screenshot upload** — photo a webinar confirmation, the agent reads it
- 📄 **CSV import** — drop in your SOA tracker export and it converts automatically
- 🔍 **Find free CPD** — ask the agent to find free guided activities online

---

## Setup Guide (Step by Step)

### Step 1 — Download the Excel Template

Download the file **`CPD_Tracker_Template.xlsx`** from this repo (click it, then click the download button).

This is your personal CPD log. All your data lives here — the agent reads and writes to it.

---

### Step 2 — Upload to Google Sheets

1. Go to **[Google Drive](https://drive.google.com)** and sign in
2. Click **New → File upload**
3. Upload the `CPD_Tracker_Template.xlsx` file you just downloaded
4. Once uploaded, right-click the file → **Open with → Google Sheets**
5. Google Sheets will convert it automatically

> Your spreadsheet has 3 tabs: **CPD Log** (your activities), **Dashboard** (auto-calculated summary), and **CPD Rules Reference** (quick cheat sheet of what qualifies).

---

### Step 3 — Publish Your Sheet (Required for the Dashboard)

The agent needs to read your sheet. Here's how to make that possible:

1. In Google Sheets, click **File** in the top menu
2. Click **Share** → **Publish to web**
3. In the first dropdown, select **"CPD Log"** (not "Entire Document")
4. In the second dropdown, select **"Comma-separated values (.csv)"**
5. Click **Publish** → click **OK** when it asks you to confirm
6. Copy the URL it gives you — it looks like this:
   ```
   https://docs.google.com/spreadsheets/d/e/LONG-ID-HERE/pub?gid=...&output=csv
   ```
7. Save this URL — you'll need it in Step 5

> ⚠️ This makes your CPD data publicly readable by anyone with the link. Since it only contains activity names and hours (no personal financial data), this is generally low risk. If you prefer privacy, you can skip the dashboard and use the agent for chat only.

---

### Step 4 — Get an Anthropic API Key

The AI chat uses Claude (by Anthropic). You need your own API key — it costs a few cents per month for typical usage.

1. Go to **[platform.anthropic.com](https://platform.anthropic.com)**
2. Sign up for a free account
3. Click **API Keys** in the left menu
4. Click **Create Key** — give it any name
5. Copy the key (starts with `sk-ant-api03-...`)

> ⚠️ Keep your API key private. Never share it publicly or paste it in a chat. The agent stores it only in your browser's local storage — it never leaves your device.

---

### Step 5 — Open the Agent and Connect Everything

1. Go to **[https://wlgccycc.github.io/SOA-CPD-AGENT](https://wlgccycc.github.io/SOA-CPD-AGENT)**
2. The setup screen will appear
3. Paste your **Published CSV URL** from Step 3
4. Paste your **Anthropic API Key** from Step 4
5. Click **Connect & Start**

Your dashboard should load with your hours automatically!

---

## How to Log a CPD Activity

Just describe it in plain English in the chat box. For example:

> *"I attended a 1.5 hour SOA webinar on IFRS 17 this morning"*

The agent will:
1. Extract the details (date, hours, type, category)
2. Ask you anything that's missing
3. Show you a formatted log card to confirm
4. Give you the row to add to your Google Sheet

You can also click the **🎤 mic button** and just speak it out loud.

---

## How to Import from SOA Tracker

If you already have activities logged in the SOA CPD Tracker:

1. Go to **[soa.org](https://www.soa.org)** → My SOA → Professional Development → CPD Tracker
2. Export your activities as a CSV file
3. In the agent, click the **📎 paperclip button**
4. Upload your CSV file
5. The agent will convert all activities to our format automatically

---

## CIA CPD Requirements (Quick Reference)

| Requirement | Amount |
|---|---|
| Total hours (2-year rolling window) | 80 hours minimum |
| Guided CPD hours | 30 hours minimum |
| Self-study hours | No minimum (counts toward 80) |
| Professionalism | Mandatory component |
| Compliance statement | Annual |
| Record keeping | 5 years |

**Guided CPD includes:** Live webinars with Q&A, in-person seminars, employer-led sessions with discussion, recorded webinars (CIA allows this)

**Self-Study includes:** Reading, books, e-learning, self-paced courses

**CIA compliance = automatic SOA compliance** for dual members ✓

---

## Frequently Asked Questions

**Does this store my data anywhere?**
No. Your CPD data lives in your own Google Sheet. Your API key is stored only in your browser's local storage. Nothing is sent to any third-party server except Anthropic's API (for the AI chat).

**How much does the API cost?**
Typical usage (logging a few activities, checking progress) costs less than $1/month. Each chat message costs a fraction of a cent.

**Can I use this if I'm only an SOA member (not CIA)?**
The dashboard is built around CIA rules. SOA-only members have different requirements — the agent can still help you track, but the compliance calculation may not be accurate for your situation.

**What if my hours show as zero?**
Make sure your Google Sheet is published correctly (Step 3). The published CSV URL must point to the "CPD Log" sheet specifically, not the entire document.

**Can multiple people use this?**
Yes! Each person sets up their own Google Sheet and connects their own API key. Everyone's data stays separate.

---

## About

This tool was built by **Shawn Yu, FSA** out of frustration with the existing CPD tracking tools — which are clunky, expensive, and don't make it easy to know if you're actually on track.

If you find this useful, share it with your actuarial colleagues. If you have suggestions, open an issue on this GitHub repo.

*For actuaries, by an actuary.*
