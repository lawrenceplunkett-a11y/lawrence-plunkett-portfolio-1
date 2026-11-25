# Lawrence Plunkett Portfolio — Implementation Plan

## Product direction
**Identity:** Creative Technology Specialist  
**Visual direction:** Premium editorial, warm neutral palette, restrained cobalt accent, expressive typography and purposeful motion.  
**Audience:** Employers, recruitment agencies, creative leaders, clients and collaborators.  
**Management:** Hybrid — custom front end with CMS-managed public content.  
**References:** Public approved testimonials plus a private reference management area.  
**CV:** Interactive career timeline with print-to-PDF support.

## Information architecture
1. Home — positioning, introduction and selected work
2. Selected work — filterable project index
3. Capabilities — six disciplines
4. About — profile and design philosophy
5. Experience — interactive career timeline
6. Endorsements — approved public recommendations
7. Contact — professional enquiries
8. Private reference workspace — authenticated, not publicly indexed

## Public content models
### Profile
- display_name
- headline
- introduction
- long_bio
- profile_image
- location_label
- contact_email
- social_links[]
- design_principle

### Project
- title
- slug
- category (brand, digital, production, systems)
- client_or_brand
- year
- summary
- challenge
- role_and_contribution
- collaborators (optional; publish only with permission)
- process
- tools_and_technology
- deliverables[]
- outcome
- evidence_metrics[]
- media[] with alt text and rights/permission status
- visibility (draft, review, published)
- featured_order

### Experience
- role_title
- organisation
- location
- start_date
- end_date
- summary
- responsibilities[]
- achievements[]
- verification_status

### Qualification
- title
- institution
- year
- credential_url (optional)
- verification_status

### Endorsement (public projection only)
- contributor_display_name
- contributor_job_title
- organisation_display_name
- relationship
- project_reference
- quote
- approved_public_fields[]
- consent_record_id
- approval_date
- publication_status

## Private reference management models
### Reference contact (private)
- id
- full_name
- job_title
- organisation
- relationship_type
- email
- LinkedIn URL (optional)
- project_association
- invitation_status
- created_at

### Reference submission (private)
- id
- reference_contact_id
- recommendation_text
- strengths_tags[]
- collaboration_context
- submitted_at
- review_status
- reviewer_notes (private)

### Consent record
- reference_submission_id
- permission_to_publish_name
- permission_to_publish_job_title
- permission_to_publish_organisation
- permission_to_publish_quote
- permission_to_link_profile
- consent_timestamp
- consent_text_version
- withdrawn_at (nullable)

**Privacy requirement:** private contact details, unapproved text and reviewer notes must never be exposed through public CMS APIs. Only approved testimonial projections should be published. Provide a way to withdraw consent and unpublish an endorsement.

## Reference workflow
1. Admin creates a contact record and sends an individual invitation.
2. Referee receives a secure, expiring, single-use submission link.
3. Referee submits their own details, relationship, project context and recommendation.
4. Explicit, granular publication permissions are collected separately from submission.
5. Admin reviews factual accuracy, sensitive information and permissions.
6. Approved endorsement is copied into the public projection; private contact data remains private.
7. Referee can request correction or withdrawal; withdrawal disables the public endorsement and is logged.

## Roles and access
- Public visitor: read published portfolio and approved endorsements only.
- Portfolio owner/admin: manage all content and reference records.
- Referee: access only their own submission through a time-limited token; cannot see other references.
- Optional editor: manage public projects but cannot access private reference contact records.

## Technical architecture
- Next.js + TypeScript application
- Reusable accessible components and responsive design tokens
- Sanity or equivalent headless CMS for public portfolio content
- PostgreSQL for private reference workflow
- Auth provider with MFA for admin access
- Server-side APIs with role checks and rate limits
- Transactional email for invitations and notifications
- Hosting with separate development, preview and production environments
- Analytics configured with privacy and consent requirements

## Build phases and acceptance criteria
### Phase 1 — Foundation
- Confirm headline, bio, visual identity and navigation
- Replace CSS demonstration artwork with approved work
- Add responsive and keyboard accessibility checks

### Phase 2 — CMS integration
- Create public schemas and editorial preview
- Enable project filtering and case-study publishing
- Add image rights, alt text and approval status

### Phase 3 — Career and CV
- Add verified roles, dates and qualifications
- Interactive timeline works on touch and keyboard
- Print stylesheet produces a legible PDF CV

### Phase 4 — Reference portal
- Authentication, single-use invitation links and expiry
- Granular consent and auditable timestamps
- Private/public data separation tested
- Withdrawal and correction workflow tested
- Spam, abuse and data-retention controls

### Phase 5 — Launch
- Accessibility review (WCAG 2.2 AA target)
- Performance, SEO, metadata and structured data
- Privacy notice, cookie controls if needed, and retention policy
- Domain, backups, monitoring and deployment runbook

## Content still required from Lawrence
- Approved headshot and preferred contact email
- Correct career chronology, employers and dates
- Exact qualification titles, awarding institutions and years
- 6–10 original project examples with images and personal contribution
- Evidence for measurable outcomes, if available
- Referee names and contact details (kept private), with their permission to invite
- LinkedIn URL and any other public professional links
