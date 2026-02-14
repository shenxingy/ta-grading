# TA Grading Project

This project is for grading student programming assignments.

## Project Structure

```
ta-grading/
  grading-rubric.md       # Universal rubric for all assignments
  templates/              # Reusable grading templates
  hw{N}/                  # Each assignment
    requirements/         # Assignment-specific requirements and instructions
    reference/            # Expected output, screenshots, reference materials
    submissions/          # Student submissions (git cloned or copied)
    grades.md             # Grading results
```

## Grading Workflow

1. Read the rubric and assignment requirements in `hw{N}/requirements/`
2. Review reference materials (expected output, screenshots, etc.) in `hw{N}/reference/`
3. Clone or copy student submission into `hw{N}/submissions/{student-name}/`
4. Review code, run the project if needed, compare against requirements
5. Record grades in `hw{N}/grades.md`

## Grading Philosophy

- **Focus on demonstrated understanding**, not surface-level details
- If a student shows they've mastered a concept but missed a minor detail elsewhere, minimal or no deduction
- Deduct heavily only when the student clearly hasn't grasped the core concept
- Be consistent with previous grading rounds (check prior hw grades for reference)
- When in doubt, give the student the benefit of the doubt

## Environment Variables

If assignments require external APIs or credentials, store them in `api-keys.env` at the project root.
If a student uses environment variables, set them before running:

```bash
source api-keys.env
```

Check the student's `.env.example`, README, or code to determine the correct variable names.

## Manual Review Setup

After cloning a student's repo, prepare it so the TA can easily run and test:

1. **Do NOT rewrite or restructure their code** — keep their original code as-is
2. Fix build/run configuration if needed (e.g., missing scripts, dependency issues)
3. Create a `run.sh` script at `submissions/{student}/run.sh` that:
   - Installs dependencies
   - Injects any required environment variables
   - Starts the project
4. Goal: TA runs `bash run.sh` and can immediately test the submission
