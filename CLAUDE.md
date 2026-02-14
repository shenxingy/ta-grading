# TA Grading Project

This project is for grading React/TypeScript student assignments.

## Project Structure

```
ta-grading/
  grading-rubric.md       # Universal rubric for all assignments
  templates/              # Reusable grading templates
  hw{N}/                  # Each assignment
    requirements/         # Assignment-specific requirements and instructions
    reference/            # Figma screenshots, expected output, reference materials
    submissions/          # Student repos (git cloned)
    grades.md             # Grading results
```

## Grading Workflow

1. Read the rubric and assignment requirements in `hw{N}/rubric/`
2. Review reference materials (Figma screenshots, etc.) in `hw{N}/reference/`
3. Clone student repo into `hw{N}/submissions/{student-name}/`
4. Review code, run the app if needed, compare against requirements
5. Record grades in `hw{N}/grades.md`

## Grading Philosophy

- **Focus on demonstrated understanding**, not surface-level details
- If a student shows they've mastered a concept but missed a minor detail elsewhere, minimal or no deduction
- Deduct heavily only when the student clearly hasn't grasped the core concept
- Be consistent with previous grading rounds (check prior hw grades for reference)
- When in doubt, give the student the benefit of the doubt

## API Keys

If assignments require external APIs, store keys in `api-keys.env` at the project root.
If a student uses environment variables for the API key, set it before running:

```bash
source api-keys.env
export API_KEY
```

Check the student's `.env.example`, README, or code to determine the correct variable name.

## Tech Stack

- React + TypeScript (Vite)
- Backend: Express with CORS (if applicable)

## Manual Review Setup

After cloning a student's repo, prepare it so the TA can run with:

```bash
pnpm i && pnpm dev
```

If the student's project structure is non-standard or won't run out of the box:
1. **Do NOT rewrite or restructure their code** — keep their original code as-is
2. Add a `package.json` at the root (or fix the existing one) with proper scripts
3. If it's a monorepo (client + server), set up a root `package.json` with:
   ```json
   {
     "scripts": {
       "dev": "concurrently \"pnpm --filter server dev\" \"pnpm --filter client dev\"",
       "dev:client": "pnpm --filter client dev",
       "dev:server": "pnpm --filter server dev"
     }
   }
   ```
   Or simpler: just document in a note what commands to run.
4. If the student has separate repos for frontend and backend:
   - Clone both into their submission folder (e.g., `submissions/{student}/client`, `submissions/{student}/server`)
   - Create a `run.sh` script at `submissions/{student}/run.sh` that:
     - Installs dependencies for both
     - Injects any required API keys
     - Starts both server and client concurrently
5. If the student has a single repo, still create `run.sh` for consistency
6. Goal: TA runs `bash run.sh`, opens browser, visually checks the app
