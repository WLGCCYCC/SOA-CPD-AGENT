# ⚖️ CPD Agent — CIA & SOA Continuing Professional Development Tracker

**Built by Shawn Yu, FSA — for actuaries, by an actuary.**

Tired of manually tracking your CPD hours? This AI-powered agent helps you log activities, track your progress toward CIA and SOA requirements, and find free guided CPD — all in one place.

> 🇨🇦 Designed for Canadian actuaries who are dual members of the **CIA** and **SOA**. Meeting the CIA requirement automatically satisfies the SOA requirement.

> ⚠️ **Disclaimer:** This is an experimental, independently-built tool and is **not affiliated with or endorsed by the CIA or SOA**. It may contain bugs, miscalculations, or classification errors. You are solely responsible for verifying your own CPD compliance and for what you submit in your official compliance statement. Always double-check entries and totals against the actual CIA/SOA requirements before relying on them.

---

## What It Does

- 📊 **Live dashboard** — see your total, guided, and self-study hours at a glance
- 🧘 **Professionalism tracking** — know if you've met the mandatory professionalism requirement
- 📅 **Pace tracking** — see how your hours are spread across the rolling 2-year window
- 🤖 **AI chat agent** — describe what you did and it helps you log it
- 🎤 **Voice input** — speak your activity instead of typing
- 📸 **Screenshot upload** — photo a webinar confirmation, the agent reads it
- 📄 **CSV import** — drop in your SOA tracker export and it converts automatically
- 🔍 **Find free CPD** — ask the agent to find free guided activities online, cached in a shared library to save tokens

---

## How Logging Actually Works (Important)

The agent **cannot write directly to your Google Sheet**. Reading your sheet (for the dashboard) uses a public read-only CSV link, but writing requires deeper Google API setup that this version doesn't include yet.

When you log an activity, the agent prepares a formatted entry and shows you a card — **you then manually copy that row into your Google Sheet.** It takes about 10 seconds per activity. Until a future version adds real write access, this manual step is part of the workflow.

---

## Setup Guide (Step by Step)

### Step 1 — Download the Excel Template

Download the file **`1_CPD_Tracker_Template.xlsx`** from this repo (click it, then click the download button).

This is your personal CPD log. It has 4 tabs:
- **CPD Log** — your activities
- **Dashboard** — auto-calculated summary
- **CPD Rules Reference** — quick cheat sheet of what qualifies
- **Free CPD Library** — shared list of free guided CPD resources (saves everyone tokens)

---

### Step 2 — Upload to Google Sheets

1. Go to **[Google Drive](https://drive.google.com)** and sign in
2. Click **New → File upload**
3. Upload the template file you just downloaded
4. Once uploaded, right-click the file → **Open with → Google Sheets**

---

### Step 3 — Publish Your Sheets (Required for the Dashboard)

You'll publish **two tabs** — CPD Log and Free CPD Library — each as their own CSV link.

For each tab:
1. In Google Sheets, click **File → Share → Publish to web**
2. In the first dropdown, select the specific tab (e.g. "CPD Log")
3. In the second dropdown, select **"Comma-separated values (.csv)"**
4. Click **Publish** → confirm
5. Copy the resulting URL

You'll end up with two separate CSV URLs — one for your log, one for the shared library. Save both.

> ⚠️ This makes that tab's data publicly readable by anyone with the link. It only contains activity names, hours, and free resource links — no financial or personal data.

---

### Step 4 — Get an Anthropic API Key

1. Go to **[platform.anthropic.com](https://platform.anthropic.com)**
2. Sign up for a free account
3. Click **API Keys → Create Key**
4. Copy the key (starts with `sk-ant-api03-...`)

> ⚠️ Never share your API key publicly. The agent stores it only in your browser's local storage.

**Cost:** typical usage runs well under $1/month. Each message costs a fraction of a cent. The agent trims conversation history and caches free CPD results to keep costs low.

---

### Step 5 — Open the Agent and Connect Everything

1. Go to **[https://wlgccycc.github.io/SOA-CPD-AGENT](https://wlgccycc.github.io/SOA-CPD-AGENT)**
2. Paste your **CPD Log CSV URL**, your **Free CPD Library CSV URL** (optional), and your **API key**
3. Click **Connect & Start**

---

## How to Log a CPD Activity

Describe it in plain English, or click the 🎤 mic and speak it:

> *"I attended a 1.5 hour SOA webinar on IFRS 17 this morning"*

The agent extracts the details, asks about anything missing, and shows a card with the row to copy into your sheet.

---

## How to Import from SOA Tracker

1. Export your activities as CSV from the SOA CPD Tracker
2. Click the **📎 paperclip button** in the agent and upload the file
3. The agent converts everything to our format

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

*(Always verify current rules directly with the CIA/SOA — this table is a convenience reference, not an authoritative source.)*

---

## Frequently Asked Questions

**Does this store my data anywhere?**
No. Your CPD data lives in your own Google Sheet. Your API key is stored only in your browser's local storage. Nothing goes to a third-party server except Anthropic's API for the AI chat.

**How much does the API cost?**
Typically under $1/month for normal use.

**Can multiple people use this?**
Yes — each person sets up their own Google Sheet and API key. Data stays separate. The Free CPD Library tab can optionally be shared across friends to pool resource discovery.

**What if my hours show as zero or wrong?**
Make sure your Google Sheet is published correctly (Step 3), and that the CSV URL points to the specific tab, not the whole document.

**Is this officially affiliated with the CIA or SOA?**
No. This is an independent tool built by an actuary for personal and community use. It is not endorsed by either organization. Always verify compliance through official channels.

---

## About

Built by **Shawn Yu, FSA** out of frustration with existing CPD tracking tools. Shared with the actuarial community in the spirit of making this easier for everyone.

*For actuaries, by an actuary. Use at your own risk — and always double-check your numbers.*
