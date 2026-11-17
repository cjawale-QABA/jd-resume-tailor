---
name: "jd-resume-tailor"
description: "Use when someone pastes a job description: build a tailored, honest resume from their resume knowledge base, roast it as a recruiter, fix red flags and ATS issues, and deliver a .docx."
---

# JD resume tailor

## Settings (edit before installing)

```
KNOWLEDGE_BASE_PATH: <set me>
OUTPUT_FOLDER: <set me>
PAGE_SIZE: A4
TARGET_PAGES: 2
```

- KNOWLEDGE_BASE_PATH: full path to your resume knowledge base .md file on your computer (start from Resume_Knowledge_Base_TEMPLATE.md, which ships in this folder).
- OUTPUT_FOLDER: folder on your computer where finished resumes are saved. Leave as <set me> to only receive the file in the chat.
- PAGE_SIZE: A4 or Letter.

## How to use

The only input is a job description. Everything about the person comes from their knowledge base, so no resume needs to be attached. Run the whole pipeline by default. The person can also ask for one stage ("roast only", "ATS scan", "cover letter", "connection note to X").

## 1. Find the knowledge base

Try these in order and use the first that works:
1. A knowledge base .md file attached to the message.
2. KNOWLEDGE_BASE_PATH from Settings, if it is set: read it with the device tools when the person's computer is linked. If its folder is not connected yet, request access to that folder once, then stage and read the file.
3. A path saved earlier in the person's memory, in a note titled "resume tailor settings".
4. None of the above: first-run setup. Ask the person for the full path to their knowledge base (or to attach it). Offer the template if they have none. When they give a path, save it to memory as "resume tailor settings" when a memory tool is available, so they are not asked again.

Also read anything in the person's memory about their job search and work history. When the knowledge base and a newer memory note disagree, the newer note wins.

The knowledge base sections are the building blocks: headline options (2), timeline (3), summary variants (4), skills bank (5), experience bank (6), certifications (7), tailoring playbook with the person's standing rules (8), do-not-claim list (9) and verified metrics (10). The person's standing rules in section 8 override the defaults in this skill.

## 2. Read the job description

Extract: job title, must-haves, nice-to-haves, years of experience, degree, languages, location and on-site days, contract type, rate or salary, sector and exact tool names. Keep the job's own wording for keywords.

## 3. Fit check before building

For every must-have, mark it Found (with the fact), Bridge (transferable, honest wording only) or Gap.
- Found: use the real detail, inside the job where it happened.
- Bridge: use honest wording such as "Tool X-equivalent experience with Tool Y", "coordinated with the team that did X" or "learning X". Never claim hands-on use.
- Gap: leave it out.
- Unknown (not in any source): ask with AskUserQuestion pop-ups, up to 4 questions per pop-up, with choices to tap. Ask all of them before building. Without pop-ups, ask in one numbered message.
- Hard blockers (a mandatory language, more years than the person has, a required sector): say so in one line and ask whether to continue.

## 4. Build the resume

- Headline: the closest option from section 2, using the job title's words where honest.
- Summary: start from the closest variant in section 4, swap in the job's keywords, 100 to 130 words. State total years in the first line when the job sets a minimum.
- Skills: a bold label per line, only categories and tools the job asks for or that support them.
- Most recent job: 8 to 10 bullets, must-haves first, with the job's title words inside one bullet. Older jobs: 2 to 4 bullets each.
- Career break, if any: its own section after experience, with an honest date line.
- Certifications, languages and education: one item per line.

Writing rules:
- Google XYZ on bullets with a verified number: result first, then the number, then how, as a plain sentence.
- Only numbers from section 10. Never invent one; ask instead.
- Nothing from section 9.
- Plain human wording: no dashes, no first person, no bold labels inside bullets, no filler words or hype.

## 5. Roast and fix

Act as a senior recruiter with 10+ years in the person's field and market who also screens CVs through an ATS. Judge the built resume on its text and the job text only.

1. Score out of 100 with a one-line verdict.
2. Requirement table: Requirement, Status (Met, Half met, Missing), Where it shows.
3. Missing keywords, including the exact job title.
4. One-minute red flags, most serious first: years against dates, gaps, title and seniority fit, leftovers from other applications, contradictions, claims that are not shown.

Fix every flag that wording can fix, using the knowledge base, and ask about any flag that needs a new fact. Rebuild and re-score once. Report both scores.

## 6. ATS check

Act as an ATS parser (Workday, Taleo, Bullhorn, Textkernel style) and check the file: no tables, text boxes, columns, images, headers or footers; plain characters; real Word heading styles with standard names; extractable contact details; each job as a title line then "Employer, Country | Mon YYYY - Mon YYYY"; acronyms spelled out once; one certificate and one language per line; document language set; author set to the person's name. Apply all fixes and report a parse-readiness score.

## 7. Build and deliver

- Word .docx, PAGE_SIZE from Settings, Arial 10 pt, name bold 16 pt, a coloured headline line, Heading 2 section titles with a thin rule, real Word bullets, TARGET_PAGES pages.
- Section order: Summary, Skills, Professional Experience, Career Break (if any), Certifications, Languages, Education.
- File name: <First>_<Last>_<Role>.docx, never a company name.
- Render to PDF, look at every page, fix overflows, then send the .docx. If OUTPUT_FOLDER is set and the computer is linked, save it there too.

Reply with: final match score and ATS score, the file, the honest gaps left out, and the 2 or 3 questions a recruiter is likely to ask. Keep it short.

## Optional extras

- Cover letter (only when asked): under 300 words, human tone, a hook on the company's or role's challenge, the top 3 matching accomplishments, why the person fits, a clear call to action.
- LinkedIn connection note (only when asked): two drafts of 200 characters or fewer with the count shown; first name, the role, one line of proof, a simple ask, signed with the person's first name.

## After every resume

If a memory tool is available, save one line about the role, both scores, the file name and any new facts the person confirmed, so later runs can use them.