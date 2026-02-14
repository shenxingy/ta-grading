# TA Grading

A structured grading framework for student programming assignments, designed to work with [Claude Code](https://docs.anthropic.com/en/docs/claude-code) (or any AI coding assistant that reads project-level instructions).

It provides a reusable rubric, organized directory structure, and templates to help TAs grade consistently, fairly, and efficiently.

## Why Use This?

- **Consistency** — A shared rubric ensures every student is graded by the same standards
- **Speed** — AI reviews code structure and logic; you focus on manual testing and edge cases
- **Transparency** — Students get clear, constructive feedback with rubric-aligned deductions
- **Reusability** — Same framework works across assignments and semesters

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI (or another AI assistant that supports project-level config files)
- Git (for cloning student repos)

## Quick Start

```bash
# 1. Clone this repo
git clone https://github.com/shenxingy/ta-grading.git
cd ta-grading

# 2. Set up environment variables (if your assignments need API keys)
cp api-keys.env.example api-keys.env
# Edit api-keys.env with your actual keys

# 3. Create your first assignment
cp -r hw-example hw1

# 4. Add assignment materials
#    - Put the assignment spec in hw1/requirements/
#    - Put expected output, screenshots, etc. in hw1/reference/

# 5. Clone a student submission
git clone <student-repo-url> hw1/submissions/student-name/repo

# 6. Open Claude Code and start grading
claude
> Grade the submission in hw1/submissions/student-name/
```

## Project Structure

```
ta-grading/
├── CLAUDE.md                # AI assistant instructions (read automatically by Claude Code)
├── grading-rubric.md        # Universal rubric — customize for your course
├── api-keys.env.example     # Environment variable template
├── templates/
│   └── grade-template.md    # Grade table template for recording results
└── hw{N}/                   # One directory per assignment
    ├── requirements/        # Assignment spec, instructions
    ├── reference/           # Expected output, design mockups, sample solutions
    ├── submissions/         # Student submissions (gitignored — never committed)
    │   └── {student}/
    │       ├── repo/        # Cloned student code
    │       └── run.sh       # One-command setup & run script
    └── grades.md            # Final grades (copy from templates/grade-template.md)
```

## Customization

This framework is designed to be adapted to your course. Here's what to change:

### Rubric (`grading-rubric.md`)

- **Point totals** — Default is 50 pts. Change the category weights to match your syllabus.
- **Categories** — The default 4 categories (Follows Directions, Quality, Required Function, Timeliness) work for most programming courses. Add or remove as needed.
- **Deduction ranges** — Adjust severity to match your course expectations.
- **Score target** — The default philosophy is generous (45-50 range). Tighten or loosen as appropriate.

### AI Instructions (`CLAUDE.md`)

This file is read automatically by Claude Code when you open the project. Customize it to:

- Describe your course's tech stack (e.g., "Python + Flask", "Java + Spring Boot", "React + TypeScript")
- Add course-specific grading notes or conventions
- Specify how to run student projects in your environment

### Environment Variables (`api-keys.env`)

If your assignments require API keys (e.g., weather APIs, database credentials), add them here. The `.gitignore` ensures they are never committed.

## Tips

- **Never commit student work** — The `.gitignore` excludes `hw*/submissions/` by default. Keep it that way.
- **Use `run.sh` scripts** — For each submission, create a `run.sh` that installs deps and starts the project. This makes manual review fast and reproducible.
- **Grade in batches** — Open Claude Code, point it at a submission, and let it do the code review. Then do your manual testing. Record results in `grades.md`.
- **Keep feedback constructive** — Explain *why* points were deducted and suggest improvements. Students learn more from good feedback than from a number.

## Ethics Guidelines

AI-assisted grading is a powerful tool, but it must be used responsibly. Please follow these guidelines:

### Before You Start

1. **Get explicit permission from the course instructor** before using AI-assisted grading. The instructor should be aware of and approve the workflow.
2. **Understand your institution's policies** on AI usage in academic contexts. Some institutions may have specific rules about automated grading.

### What AI Is Good At (and What It Isn't)

This project was born from a practical problem: students' project structures vary wildly — different folder layouts, different package managers, missing scripts, monorepos vs single repos. Getting each submission to simply *run* can take more time than actually reviewing the code.

**The primary goal of AI here is to:**
- Wrap each student's project in a consistent `run.sh` interface *without modifying their code*, so TAs can launch any submission with one command
- Perform an initial code review — checking logic, structure, and whether required features are implemented
- Save deployment/setup time so TAs can focus on what matters: evaluating the actual work

**What you MUST do yourself:**
- **UI/UX review** — AI cannot visually verify layouts, styling, responsiveness, or interaction flows. You must open the app and check it against design specs yourself.
- **Backend verification** — Test API endpoints, database operations, and edge cases manually. AI may miss runtime issues, race conditions, or subtle bugs.
- **Final judgment** — AI suggestions are a starting point, not a verdict. Always apply your own judgment before assigning a final grade.
- **Feedback quality** — Review and edit AI-generated feedback before sharing with students. Make sure it's accurate, fair, and constructive.

### In Short

**AI assists; you decide.** Never assign a grade based solely on AI output. Treat AI as a first-pass reviewer that saves you setup time and catches obvious issues — the final grading responsibility is always yours.

## Disclaimer

This project is provided as-is for educational and productivity purposes. The developer(s) make no guarantees about grading accuracy and accept **no responsibility** for any academic integrity investigations, disputes, or consequences arising from the use of this tool. It is the user's sole responsibility to ensure that their use of AI-assisted grading complies with their institution's policies and ethical standards.

## License

MIT
