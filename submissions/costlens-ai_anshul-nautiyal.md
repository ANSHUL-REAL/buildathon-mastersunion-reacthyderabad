# Project Name

CostLens AI — HR Cost Intelligence Engine

---

## Attendee Details

**Name:** Anshul Nautiyal
**GitHub Username:** ANSHUL-REAL
**LinkedIn Profile:** https://www.linkedin.com/in/anshul-nautiyal
**GitHub Project Repository:** https://github.com/ANSHUL-REAL/CostlensAI

---

## Problem Statement Selected

HR Cost Intelligence Engine

---

## Project Description

CostLens AI converts calendar meetings into project-level HR expenditure insights, solving the visibility gap in employee time and cost distribution without invasive surveillance or tedious timesheets. It maps attendee roles and scaled salary benchmarks to calculate accurate per-meeting headcount costs, helping companies identify cost leakages, project overruns, and savings opportunities.

---

## Approach

1. **Roster Foundation**: Loaded all 1,470 employee records from the Kaggle IBM HR Analytics dataset, scaling rates to realistic INR bands and status from attrition logs to construct a real-world enterprise roster.
2. **Flexible Calendar Ingest**: Developed a robust manual `.ics` iCalendar parser alongside the Google Calendar OAuth client so that users can import their real schedules instantly (drag-and-drop) without requiring complex Google Cloud setup, or sync dynamically via OAuth.
3. **AI Project Attribution**: Integrated the Google Gemini 2.5 Flash API to classify meetings into active projects based on titles, descriptions, and attendees. Added keyword matching as a high-speed pre-pass and fallback.
4. **Minimalist Dark Void UI**: Redesigned the interface to follow a clean, sparse "cmd+zest" dark theme (`#141513`) with bright electric lime highlights (`#c1f85c`).
5. **Privacy Guarding**: Implemented a role-based switcher allowing PMs, Finance, Admins, and Leadership to access the dashboard. Individual hourly rates are masked with `•••` for non-privileged roles at both the API and UI layers.

---

## Tech Stack and Tools Used

**Frontend:** React 18, Next.js 14, HTML, CSS, Tailwind CSS, Recharts
**Backend:** Next.js App Router (Server Actions & Route Handlers)
**Database:** Supabase (PostgreSQL, Auth, RLS)
**AI Tools/API:** Google Gemini 2.5 Flash API
**Cloud/Deployment:** Vercel (Production URL: https://costlens-ai.vercel.app)
**Other Tools:** Cursor, VS Code, Git

---

## Key Features

1. **Automated AI Project Attribution**: Gemini 2.5 Flash integration with confidence scores, reasoning logs, and keyword fallback.
2. **Dual Calendar Ingest Pipeline**: Google Calendar OAuth Sync (by date range) and drag-and-drop manual iCalendar `.ics` file parser.
3. **Role-Based Privacy Switcher**: Masquerade as Admin, Finance Manager, Project Manager, or Leadership to test privacy rate masking.
4. **Anomalies & Cost Leakage Detection**: Detects budget overruns, duplicate recurring meetings, expensive meetings (₹5k+), and shadow projects.
5. **AI Cost Optimizer Recommendations**: Computes potential monthly savings with one-click apply/dismiss actions.
6. **Financial Report Exporter**: Generates detailed CSV downloads for projects, meetings, anomalies, and summaries.

---

## What is Working?

- Deployed production website on Vercel: https://costlens-ai.vercel.app
- Supabase database containing the 1,470 Kaggle employee records.
- Google Calendar OAuth consent, callback, and date-range sync.
- Drag-and-drop manual `.ics` file upload and attendee matching.
- Gemini 2.5 Flash project attribution.
- Interactive dashboard charts (Project cost, Daily trend, Budget usage, Department distribution).
- Anomaly checks, cost optimizer recommendations, and CSV exports.

---

## What is Still in Progress?

- Real-time Slack/Teams alert notifications for budget overrun warnings.
- Direct task/project sync from Jira and Linear.

---

## Screenshots or Demo

**Deployed Link:** https://costlens-ai.vercel.app
**Demo Video Link:** *Submitted separately*
**Screenshots:** *Available on Vercel deployment*

---

## Challenges Faced

- Handling Windows local filesystem incompatibilities for folders/files containing trailing whitespace (such as `'SECURITY.md '` in the remote repository) during git operations.
- Scaling and cleaning the 1,470 Kaggle employee roster data while maintaining correct name formats and unique email structures.

---

## Learnings

- Implementing SSR client-side cookies and auth guards in Next.js 14 middleware.
- Handling large batch upserts securely with Supabase database service role access.
- Deploying dynamic serverless functions on Vercel while properly managing dynamic route segments.

---

## Future Improvements

- Support Outlook / Exchange calendar live feeds.
- Forecast weekly budget overruns using historical meeting schedules.

---

## Final Note

CostLens AI is designed to make meetings financially accountable without invading employee privacy. We hope this engine empowers organizations to optimize their team's time effectively.
