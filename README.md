# Reusable Claude Code Job Search Assistant

This is a clean, reusable project for a new job seeker. It contains no candidate profile. Each person should run `/setup` with their resume attached, then review and confirm the generated profile and job-search preferences.

## Get started

Requirements: Claude Code and a resume file (PDF, DOCX, TXT, or another readable format). LaTeX is needed only to compile the provided document templates.

In PowerShell:

```powershell
Set-Location E:\appSec\sister-job-agent
claude
```

In Claude Code:

1. Attach the resume and run `/setup`.
2. Review and correct `candidate-profile.md` and the target-role preferences `/setup` records.
3. Run `/scrape` to search for jobs, or `/apply <job URL or pasted posting>` to evaluate and prepare one application.

The workflows use Claude Code's web search and fetch tools when available. They do not automate LinkedIn or apply to jobs. Search coverage depends on accessible listings; verify each role at the employer's website.

## Project files

- `.claude/skills/setup/SKILL.md`: resume-led onboarding.
- `.claude/skills/scrape/SKILL.md`: profile-driven general job search.
- `.claude/skills/apply/SKILL.md`: job fit, approval, tailored documents, verification, and archiving.
- `cv/master.tex`: blank generic LaTeX CV starting point.
- `cover_letters/cover_template.tex`: blank cover-letter starting point.
- `candidate-profile.md`: created by `/setup` and excluded from Git by default.
