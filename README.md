# jd-resume-tailor

A Claude skill that turns a pasted job description into a tailored, honest resume.

You paste a job description. The skill reads your resume knowledge base, builds a resume that matches the job, roasts it the way a recruiter would, fixes the red flags, checks it against applicant tracking systems (ATS), and gives you a Word (.docx) file. It never claims a skill, tool or number that is not in your knowledge base.

## What it does

1. Reads the job description: title, must-haves, nice-to-haves, years, languages, location, contract type and tool names.
2. Loads your facts from your knowledge base file and from Claude's memory, if you use it.
3. Sorts each requirement into **Found**, **Bridge** (transferable, worded honestly) or **Gap**, and asks you short pop-up questions only for facts it cannot find.
4. Builds the resume from your headlines, summaries, experience bullets and verified numbers.
5. Roasts the resume as a senior recruiter: match score, requirement table, missing keywords and one-minute red flags. Then it fixes them and re-scores.
6. Runs an ATS check (headings, contact details, dates, acronyms, one item per line) and fixes what it finds.
7. Delivers the .docx with both scores, the honest gaps and the questions a recruiter is likely to ask.

On request it also writes a cover letter (under 300 words) or a LinkedIn connection note (200 characters or fewer).

## What's in this repo

| File | What it is |
|---|---|
| `jd-resume-tailor/SKILL.md` | The skill itself |
| `jd-resume-tailor/Resume_Knowledge_Base_TEMPLATE.md` | A blank knowledge base to fill in with your own facts |

## Setup

### 1. Fill in your knowledge base

Copy `Resume_Knowledge_Base_TEMPLATE.md` to your computer, rename it (for example `My_Resume_Knowledge_Base.md`) and fill in all 10 sections. Two sections matter most:

- **Section 9, Do not claim:** everything you do not have. The skill never puts these on a resume.
- **Section 10, Verified metrics:** every number you are allowed to use. The skill never invents a number.

### 2. Set your variables

> [!IMPORTANT]
> **Edit these lines at the top of `jd-resume-tailor/SKILL.md` before you install the skill.** They are the only part you need to change.
>
> ```
> KNOWLEDGE_BASE_PATH: <set me>
> OUTPUT_FOLDER: <set me>
> PAGE_SIZE: A4
> TARGET_PAGES: 2
> ```

| Variable | Required | What to put there | Example |
|---|---|---|---|
| **`KNOWLEDGE_BASE_PATH`** | **Yes** | Full path to your filled-in knowledge base .md file | `/Users/yourname/Documents/job search/My_Resume_Knowledge_Base.md` |
| **`OUTPUT_FOLDER`** | No | Folder where finished resumes are saved. Leave `<set me>` to only get the file in the chat | `/Users/yourname/Documents/job search` |
| **`PAGE_SIZE`** | No | `A4` (Europe and most of the world) or `Letter` (US and Canada) | `A4` |
| **`TARGET_PAGES`** | No | How many pages the resume should fit on | `2` |

> [!NOTE]
> If you leave `KNOWLEDGE_BASE_PATH` as `<set me>`, the skill asks for the path (or for the file) the first time you use it. If your Claude has memory turned on, it saves the path so it asks only once. You can also attach the knowledge base file to any message instead.

Reading the file from a path on your computer needs the Claude desktop app linked to your chat. Without that, attach the knowledge base file to the message.

### 3. Install the skill

Zip the `jd-resume-tailor` folder (the folder, with `SKILL.md` and the template inside) and add it as a custom skill in your Claude app's skills settings.

## How to use it

Paste a job description and say "tailor my resume for this", or just paste it. You can also ask for one stage:

- "Roast my resume for this job"
- "ATS scan"
- "Write a cover letter for this job"
- "Connection note to [name], 200 characters max"

## Rules the skill follows

- Only facts from your knowledge base, and newer facts you confirm in a pop-up.
- Nothing from your do-not-claim list, and no invented numbers.
- Plain human wording: no dashes, no first person, no filler words.
- File names never include the company name.

## Author

Made by [Chaitali Jawale](https://github.com/cjawale-QABA). See also [claude-skills](https://github.com/cjawale-QABA/claude-skills).
