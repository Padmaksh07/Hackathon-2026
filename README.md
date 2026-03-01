# 🚀 BridgeNE – Student Opportunity & Internship Matching Portal

BridgeNE – Student Opportunity & Internship Matching Portal
​
BridgeNE is an AI-powered matchmaking prototype designed to connect students from Northeast India with relevant internships, hackathons, and early-career opportunities. Built in a 24-hour hackathon (CodeStellation 2026) by Team Code Tandoor, it focuses on skill-based matching and clear improvement roadmaps.
​

Note: This is an early-stage prototype, so there may be bugs and incomplete flows. Active development and refinements are ongoing.

Problem
​
Opportunities are scattered across WhatsApp groups, Telegram channels, and social media.

Students often apply without understanding skill fit or gaps.

Many miss relevant roles due to lack of awareness and guidance.

Resumes exist, but students do not know how to use them effectively, leading to mismatches and missed growth opportunities.
​

Objective
​
Build a platform that:

Centralizes student opportunities (internships, hackathons, startup roles).

Matches students with relevant roles using their skills and resume.

Identifies precise skill gaps and shows how to bridge them.

Provides personalized improvement recommendations.

Supports regional/native language for better understanding.
​

Proposed Solution
​
A web platform where:

Students upload their resume or manually enter skills.

Skills are automatically extracted from resume text using an AI LLM (Google Gemini 2.5 Flash).

The dashboard dynamically updates as students add skills or as new roles are added.

Matching internships and roles are listed with a match score and visual indicators.

Missing and nice-to-have skills are highlighted, with learning recommendations per skill.
​

Core Features
​
Resume upload plus manual skill input with quick-add buttons (e.g., React, Node.js, MongoDB).

AI-powered skill extraction from raw resume text.

Opportunity dashboard with internships, startup roles, and hackathons.

Match score visualization with categories:

80%+ – Strong Match

50–79% – Good Match

<50% – Partial Match
​

Skill gap analysis:

Green: matched skills

Red: missing skills

Yellow: nice-to-have skills
​

Learning recommendations that show which missing skills unlock more opportunities.

Bookmarking for saving interesting opportunities.
​

System Workflow
​
Frontend (React) sends text/skills to backend.

Backend (Node.js + Express) prompts Gemini with the resume/skills.

Gemini returns structured JSON with extracted skills and insights.

Frontend updates UI with match scores, gaps, and recommendations.
​

Student Profile

Capture name, email, and skills (typed or selected via quick-add).

Clean and normalize skill strings so variations like "Node.js", "node js", and "Nodejs" are treated as the same skill.
​

Matching & Dashboard

Match percentage = matched skills ÷ required skills × 100 (rounded).

Display tailored opportunities with filters (type, location, skill), search, sorting (match, deadline), and visual cards.
​

Tech Stack
​
Frontend

React 18 for an interactive, component-based UI.

Vanilla CSS for full styling control.
​

Backend

Node.js + Express for APIs and matching logic.
​

Data Layer

Mock JSON files for opportunities and skills (designed to be swapped with MongoDB or another database later).

Integration with Google Gemini 2.5 Flash (AI LLM) for resume skill extraction and intelligence.
​

Impact & Future Scope
​
Immediate Impact

Students see which roles they are ready for now.

Clear visibility into which skills to learn next.

Reduced time spent searching and improved relevance of applications.

Faster discovery of regional internships and startup roles.
​

Planned Enhancements

AI-based resume feedback and scoring.

Deep personalized learning roadmaps for each student.

Regional language support to make the platform more inclusive.

Connecting students with Northeast alumni who have bridged similar skill gaps.
​

Current Status
Built as a functional prototype in a 24-hour hackathon.

Uses mock data for opportunities (around 10 example internships and hackathons).

Expect incomplete flows and potential bugs; active improvements are planned before production use.
​

Team – Code Tandoor
Built with passion by Team Code Tandoor at CodeStellation 2026.​
Padmaksh Paul
Kirtiman Bhattacharjee 
Akashdip Sarma 
Koushtav boruah
