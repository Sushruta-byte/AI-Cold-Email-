# 🧊 Cold Emailr — AI-Powered Cold Email Automation Tool

**Cold Emailr** is a full-stack AI agent that automates personalized cold outreach at scale. It's built to help job seekers and professionals generate tailored emails using OpenAI, attach a resume, log sent messages in Google Sheets, and set up smart follow-ups — all through a sleek frontend deployed on Vercel and a no-code backend powered by n8n.

---

## 🚀 Features

- ✉️ Sends personalized emails to multiple recipients using AI
- 📎 Automatically attaches your latest resume from Google Drive
- 🧠 Matches your resume to the job description + company values
- 📊 Logs every email sent in a Google Sheet
- 🔁 Sets auto-follow-up reminders for 3 days later
- 💻 Frontend built in Next.js + Tailwind CSS
- 🛠 Backend automation with [n8n](https://n8n.io/)
- 📡 Triggerable via webhook from Vercel frontend

---

## 🖥️ Frontend — Built with Next.js & Deployed via Vercel

### 🔧 Tech Stack

- React (Next.js 15)
- Tailwind CSS
- Shadcn/UI + Radix UI
- Axios + React Hook Form
- TypeScript

### 🧩 UI Features

- Form fields for:
  - Job Title
  - Job Description
  - Company Name
  - Dynamic recipient list (Name + Email)
- Sends form data to your n8n webhook
- Toast alerts for success/failure
- Clean, minimal responsive layout

### ▶️ Local Setup

```bash
git clone https://github.com/your-username/cold-emailr.git
cd cold-emailr
npm install
npm run dev
```



## 🧠 Backend — n8n AI Email Workflow

### 🔁 Workflow Steps:

1. **Webhook Trigger**
2. **Code Node** — Flattens input data
3. **Set Node** — Injects static resume summary
4. **OpenAI Node** — Generates personalized HTML email
5. **Google Drive Node** — Downloads resume using File ID
6. **Gmail Node** — Sends email with:
   - Recipient info
   - AI-generated content
   - Resume PDF attached
7. **Google Sheets Node** — Appends row to track:
   - Recipient
   - Job details
   - Timestamp
   - Follow-up date (3 days later)

---

## 📎 Resume Attachment (Google Drive)

- Resume is stored in Google Drive
- Resume is fetched using a Service Account via the Google Drive API
- Gmail node attaches the binary `data` as a PDF file

To update your resume, just replace the file in Drive — no workflow changes needed.

---

## 📊 Email Logging (Google Sheets)

- Tracks each email sent with:
  - Name
  - Email
  - Job title & company
  - Sent timestamp
  - Auto follow-up date
- Sheet is updated using Google Sheets API`

---

## 👨‍💻 Built By

Sushruta Das  
Made with ❤️ using Next.js, Vercel, n8n, and OpenAI.

---
