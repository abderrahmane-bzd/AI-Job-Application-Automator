# AI Job Application Automator

Automatically generate a personalized, ATS-ready cover letter with AI and send it — CV attached — in one command.

## What it does

Give it a company name, a company description, and a job posting, and this script will:

1. **Read your CV** (PDF) and understand your real experience and skills
2. **Generate a tailored cover letter** with Google's Gemini AI — matched to the specific job and company, never generic or copy-pasted
3. **Convert it to a polished PDF**
4. **Email it automatically** to the recruiter, with both the cover letter and your CV attached

What used to take 15–20 minutes per application (writing, formatting, attaching, sending) now takes under a minute.

## Why this matters for your business

This isn't just a cover-letter tool — it's a template for a common automation pattern:

> **Structured input → AI-generated personalized content → auto-formatted document → auto-sent**

The same architecture can be adapted for:

- 📄 Automated quote / proposal generation for sales teams
- ✉️ Personalized follow-up or outreach emails at scale
- 📋 AI-generated reports sent on a schedule
- 🤝 Any workflow that needs a personalized document, generated and delivered without manual work

If you need something similar for your business, this project is a working proof of concept of exactly that kind of automation.

## Tech stack

| Component | Tool |
|---|---|
| AI content generation | Google Gemini API |
| PDF generation | ReportLab |
| Email delivery | Python `smtplib` / Gmail SMTP |
| Language | Python 3 |

## How it works

```
Your inputs (company, job description, CV)
        │
        ▼
  Gemini AI generates a
  tailored cover letter
        │
        ▼
  Cover letter rendered as PDF
        │
        ▼
  Email sent automatically with
  cover letter + CV attached
```

## Setup

**1. Clone the repo and install dependencies**
```bash
git clone https://github.com/abderrahmane-bzd/AI-Job-Application-Automator
cd ai-job-application-automator
pip install -r requirements.txt
```

**2. Add your credentials**

Copy the example environment file and fill in your own values:
```bash
cp config.example.py
```

You'll need:
- A [Gemini API key](https://ai.google.dev/) (free tier available)
- A Gmail [App Password](https://myaccount.google.com/apppasswords) (not your regular password)

**3. Add your CV**

Place your CV as `cv.pdf` in the project folder.

**4. Run it**
```bash
python main.py
```
You'll be prompted for the company name, company description, job title, job description, and the sender's contact details — the script handles the rest.

## Example output

A cover letter generated for a real job posting, tailored to the specific role and company, formatted as a clean one-page PDF, delivered straight to the recruiter's inbox — no manual writing, formatting, or attaching involved.

## Customize it

Everything is modular and easy to adapt:
- `prompt.py` — edit the AI instructions to change tone, language, structure, or length
- `main.py` — swap the email logic, add new input fields, or plug in a different AI provider

## Want something like this for your workflow?

This project shows the pattern — I build custom versions of this kind of automation (AI content generation + document creation + auto-send) tailored to your specific process. Get in touch if you'd like to discuss your use case.

## License

MIT — free to use and adapt.
