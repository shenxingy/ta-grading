# TA Grading

AI-assisted grading framework for React/TypeScript student assignments, powered by [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## How It Works

1. Place assignment requirements and reference materials (e.g., Figma screenshots) in `hw{N}/`
2. Clone student repos into `hw{N}/submissions/`
3. Claude Code reads the rubric, reviews code, and runs the app
4. TA does a manual visual review
5. Grades are recorded in `hw{N}/grades.md`

## Project Structure

```
ta-grading/
├── CLAUDE.md                # Instructions for Claude Code
├── grading-rubric.md        # Universal rubric (50 pts)
├── api-keys.env.example     # API key template
├── templates/
│   └── grade-template.md    # Grade table template
└── hw{N}/                   # Per-assignment directory
    ├── requirements/        # Assignment spec
    ├── reference/           # Figma screenshots, expected output
    ├── submissions/         # Student repos (gitignored)
    └── grades.md            # Final grades
```

## Setup

```bash
cp api-keys.env.example api-keys.env
# Fill in your API keys
```

## Usage

Open the project in Claude Code and ask it to grade a student submission:

```
> Grade the submission in hw1/submissions/student-name/
```

Claude Code will follow the rubric in `grading-rubric.md` and the assignment requirements in `hw{N}/requirements/` to produce a detailed grade with feedback.
