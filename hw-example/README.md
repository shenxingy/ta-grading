# Assignment Directory Template

Copy this directory to create a new assignment:

```bash
cp -r hw-example hw1
```

## Directory Structure

```
hw1/
├── requirements/    # Put the assignment spec here (PDF, markdown, etc.)
├── reference/       # Put expected output, design mockups, or sample solutions here
├── submissions/     # Clone student repos here (gitignored — never committed)
│   └── {student}/
│       ├── repo/    # The student's cloned repository
│       └── run.sh   # Script to install deps + run the project
└── grades.md        # Copy from templates/grade-template.md, fill in as you grade
```

## What Goes Where

- **requirements/** — The assignment handout. This is what Claude reads to understand what the student was asked to do.
- **reference/** — The "answer key": expected output screenshots, sample solutions, design mockups, test cases. This is what you compare submissions against.
- **submissions/** — One subdirectory per student. This directory is gitignored so student code is never pushed to your repo.
