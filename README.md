# AI-Job-Search-agent
An AI powered job search agent. Light of hope in dark.. makes you feel like maybe now's my chance, So if you feel like AI is taking your job, just uno reverse it and find a job using AI.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Built with Make.com](https://img.shields.io/badge/Built%20with-Make.com-6366f1)](https://make.com)
[![Powered by OpenAI](https://img.shields.io/badge/Powered%20by-OpenAI-412991)](https://openai.com)
[![Status: Active](https://img.shields.io/badge/Status-Active-brightgreen)]()

# Why I Built This
Job hunting is broken.
LinkedIn throws hundreds of jobs at your face but when you apply — silence. Not because you're unqualified, but because your resume didn't match the ATS format of that specific role. You spend hours manually searching 5 portals, copy-pasting JDs, guessing whether you match, applying blindly and waiting.
I got tired of that. So I automated it.
This pipeline runs every 3 hours, pulls live job listings from RSS feeds, uses AI to analyse and score each role against your profile, and stores everything neatly in Airtable — so every morning you wake up to a prioritised list of jobs worth actually applying to.
No more guessing. No more noise. Just signal.
### How It Works
RSS Feeds → Duplicate Check → Fetch Full JD → AI Extraction → AI Scoring → Airtable Storage
     ↑                                                                              ↓
Runs every 3 hours automatically                              Clean prioritised job board

<img width="300" height="450" alt="AI-powered job matching flowchart" src="https://github.com/user-attachments/assets/ddac47fb-4bd3-4a55-8104-e22b3a207546" />

# Pipeline Flow
# Steps       # Tool                 # Action
   1.        RSS Feed       Pulls live job listings from job portals every 3 hours.
   2.        Airtable       Checks for duplicates never processes the same job twice.
   3.        HTTP           Fetches full job description from listing URL.
   4.        Tools / Sleep  Rate limiting to stay within API thresholds.
   5.        OpenAI         Extracts structured data — title, company, location, skills.
   6.        OpenAI         Scores job relevance against your profile (0–100).
   7.        Airtable       Creates a clean record with all data for review.

# Tech Stack
# Tool                    # Purpose
Make.com          Automation workflow — orchestrates the entire pipeline
Airtable          Database — stores, organises and displays job records
OpenAI API        LLM — extracts and scores job descriptions intelligently
RSS Feeds         Data source — live job listings from multiple portals
HTTP Module       Fetches full JD content from listing URLs

# Features
Automated ingestion — runs every 3 hours without manual input
Duplicate prevention — never stores the same job twice
AI extraction — pulls title, company, location, skills, salary from raw JD text
Relevance scoring — gives each job a 0-100 match score against your profile
Apply recommendation — AI says Apply Now, Apply Later or Skip
Skills gap analysis — tells you which required skills you are missing
Kanban board — track every application from New to Applied to Interview to Offer

# What Gets Stored Per Job
{
  "job_title": "Business Analyst",
  "company": "Sciative Solutions",
  "location": "Mumbai / Remote",
  "work_type": "Hybrid",
  "skills_required": ["Power BI", "SQL", "Python", "Stakeholder Management"],
  "match_score": 84,
  "match_reason": "Strong alignment on BI tools and BA skills.",
  "apply_recommendation": "Apply Now",
  "missing_skills": ["GRC", "Risk Management"],
  "source_url": "https://...",
  "date_found": "2026-03-22",
  "status": "New"
}

# Cost
# Tool                                # Cost
Make.com                         Free (1,000 operations/month)
Airtable                         Free (up to 1,200 records)
OpenAI                           ~120 INR/month
Total when not using Gorq        ~120
Total with Groq                  0 INR/month
*** After credit expires calculated as per the cost of tool

## 📹 Demo

[![Watch Demo](https://img.shields.io/badge/Watch-Demo%20Video-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/t1OLEmLM-IA)

> See the full pipeline running — RSS ingestion → AI scoring → Airtable record creation
