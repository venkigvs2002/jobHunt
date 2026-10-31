---
name: setup
description: Set up a new person's job-search assistant from an attached resume. Extract a verified candidate profile, ask for target roles and location preferences, and save confirmed setup details. Use for /setup or onboarding a job seeker.
allowed-tools: Read, Write, Edit, Glob, AskUserQuestion
---

# Set Up a Candidate Profile

This is the onboarding workflow for a new person. Do not use any existing user's personal details. The attached resume and the candidate's answers are the only sources for their profile.

## 1. Find and read the resume

- If the user attached a resume, read the attachment. If no resume is available, ask them to attach it or provide its path, then stop until they do.
- Accept readable PDF, DOCX, TXT, Markdown, or plain-text resume content. If the file cannot be read, explain the limitation and ask for an accessible PDF or text copy.
- Do not send the resume to external services. Treat its contents as private.
- Extract only information explicitly stated: name/contact details, location, headline, experience/employers/dates, education, skills/tools, certifications, languages, projects, and measurable results.
- Do not infer missing dates, seniority, proficiency, work authorization, metrics, or credentials. Mark uncertainties for confirmation.

## 2. Ask the candidate to fill gaps and set preferences

After inspecting the resume, ask a focused set of questions. Do not ask for facts already stated clearly. Use a single structured form where possible:

- Confirm corrections or ambiguities in extracted facts.
- Target job titles, job functions, and industries.
- Country/countries and cities; whether remote, hybrid, onsite, or relocation is acceptable.
- Work authorization or sponsorship needs for each target market.
- Desired seniority and any titles, duties, industries, or conditions to exclude.
- Optional salary range and other practical constraints.

Tell the user they may say "unknown" or skip optional items. Never guess an unanswered preference.

## 3. Write the profile

Create `candidate-profile.md` with these headings, using `Not provided` for relevant unanswered fields:

```markdown
# Candidate Profile

## Identity and Contact
## Location and Work Authorization
## Target Roles and Industries
## Work Preferences and Deal-Breakers
## Languages
## Professional Summary
## Experience
## Education
## Skills and Tools
## Certifications
## Projects and Achievements
## Open Questions
```

Separate resume-supported facts from candidate-confirmed additions. Omit empty sections when appropriate, but preserve explicit unknowns that matter to job eligibility. Never invent or inflate.

Create or update `job_tracker.csv` only if it does not exist; preserve any existing records. Do not create sample applications. Do not modify the templates or workflow skills during onboarding.

## 4. Review with the user

Summarize what was recorded and list unresolved questions. Ask the user to check `candidate-profile.md` and correct it before relying on `/scrape` or `/apply`. Do not claim setup is complete if the resume could not be read or the user has not been shown the extracted profile.
