# NextHack-AI
a full-stack security testing application for internal teams to run authorized, scope-locked web app assessments with auditability, role-based controls, and AI-assisted analysis.

# What this app does
- Runs authorized vulnerability scans against predefined scope (domains, techniques, rate limits), with explicit engagement controls.
- Uses a Coordinator + Solver architecture for scalable scan orchestration (job queue, concurrent workers, findings graph, progress tracking).
- Produces actionable findings with severity/confidence, CWE/OWASP mapping, remediation guidance, and validation metadata.
- Integrates AI-assisted reasoning and redteam enrichment for findings triage and next-scan recommendations.
- Supports admin governance via audit logs, role-based access, and secure operational workflows.
- Exports findings/reports in multiple formats for internal and external reporting use cases.

<img width="1424" height="788" alt="Screenshot 2026-04-24 at 11 25 03 AM" src="https://github.com/user-attachments/assets/0ae987c8-b327-4efa-8400-90ffb67ed73d" />

<img width="1430" height="799" alt="Screenshot 2026-04-24 at 11 25 39 AM" src="https://github.com/user-attachments/assets/6aa9a9ee-c8db-4612-833f-19f2a930e35b" />



# Core Features
Authentication + session management with RBAC (viewer, analyst, admin)
Scope and target management with lock controls during active engagements
Scan lifecycle APIs (draft/start/run/stop/complete) with live progress/log updates
Advanced scanner checks (headers, transport, reflection/XSS validation, SQLi exploitation workflow, path/traversal checks, CORS, etc.)
Browser-assisted security validation via Playwright (DOM/XSS and SPA endpoint discovery)
CAI-based artifact reasoning and finding enrichment pipelines
Findings workflow (review, validate/unvalidate, detail view, evidence handling)
Report export endpoints (JSON + platform-friendly formats)
Separated backend responsibilities (core app backend vs dedicated email delivery backend)

# Tech Stack
Frontend: Next.js 14, React, TypeScript, Tailwind CSS, Radix UI
Backend (app): Next.js App Router API routes (TypeScript)
Backend (aux): FastAPI (Python) for CAI/email support services
Database/ORM: SQLite + Prisma
Security/AI: Custom scanner engine, Coordinator/Solver execution model, CAI integrations
Browser automation: Playwright (Chromium)

