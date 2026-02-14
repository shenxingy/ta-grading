# TA Grading

A structured grading framework for React/TypeScript student assignments. Provides a reusable rubric, organized directory structure, and templates for consistent and fair grading across assignments.

## How It Works

1. Place assignment requirements and reference materials (e.g., Figma screenshots) in `hw{N}/`
2. Clone student repos into `hw{N}/submissions/`
3. Review code against the rubric and assignment requirements
4. Run the app and do a visual review against reference designs
5. Record grades in `hw{N}/grades.md`

## Project Structure

```
ta-grading/
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
# Fill in your API keys (if assignments require external APIs)
```

## Usage

1. Copy `hw-example/` to `hw1/` (or `hw2/`, etc.)
2. Add the assignment spec to `hw1/requirements/`
3. Add Figma screenshots or expected output to `hw1/reference/`
4. Clone each student's repo into `hw1/submissions/{student}/`
5. Grade using `grading-rubric.md` and record results in `hw1/grades.md`
