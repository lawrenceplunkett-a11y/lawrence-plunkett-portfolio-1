# Lawrence Plunkett — Portfolio prototype

A responsive, editorial-style portfolio prototype built with plain HTML, CSS and JavaScript.

## Run locally

Open `index.html` in a modern browser. For a local server, run:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Included
- Responsive editorial homepage and navigation
- Project category filters and six interactive case-study panels
- Capabilities, profile and design philosophy sections
- Interactive career timeline
- Print / Save as PDF CV action
- Professional endorsement placeholder
- Contact section

## Important before public launch
This is a front-end prototype, not a deployed website or production CMS. Project cards contain illustrative CSS artwork and draft copy. Replace them with original assets and verified project facts. Confirm career dates, qualifications, role descriptions, contact details and social links.

The requested private reference management and public endorsement workflow is specified in `IMPLEMENTATION-PLAN.md` but is not yet connected to a database. Do not collect real private reference data in this prototype. Production implementation requires authentication, server-side storage, access controls, consent records, spam protection and a secure submission workflow.

## Recommended production architecture
- Next.js + TypeScript for the application
- Tailwind CSS or CSS modules for styling
- Sanity (or equivalent headless CMS) for public profile, projects, case studies and approved testimonials
- Authenticated server-side reference portal with role-based access
- PostgreSQL-backed reference records, encrypted transport, least-privilege access and audit trail
- Email provider for invitation and approval notifications
- Vercel or equivalent hosting with preview and production environments

See `IMPLEMENTATION-PLAN.md` for the build sequence and content model.
