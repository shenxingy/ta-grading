# TA Grading Rubric

**Total: 50 Points**

> **Core Principle:** Focus on whether the student has demonstrated mastery of the
> underlying concepts. If a minor detail is missed but competence is clearly shown
> elsewhere, apply minimal or no deduction. Deduct heavily only when the student
> clearly has not grasped the core concept.
>
> **Score Target:** Most students should score 45-50. The floor is 40+.
> Be generous — prefer giving the benefit of the doubt. Only deduct when
> there's a clear, meaningful gap in understanding. Small issues that don't
> reflect a lack of skill should cost at most 1 point, or nothing at all.

---

## I. Workflow

1. **AI Static Analysis** — Inspect logic, structure, code quality, and technical
   requirements defined in the assignment description.
2. **Manual Review** — Verify UI fidelity against Figma designs, assess interaction
   flow and usability.

---

## II. Rubric Categories

### 1. Follows Directions (5 pts)

Compliance with administrative, structural, and submission requirements.

| Issue | Deduction | Notes |
|-------|-----------|-------|
| Naming violation | -1 to -2 | Files/folders don't follow the specified naming convention. If the intent is clear and everything works, lean toward -1. |
| Documentation issues | -2 to -3 | Missing or incomplete README.md that prevents smooth setup/execution. |
| Submission error | -5 | Wrong platform, invalid repo link, or inaccessible work. |

### 2. Quality (15 pts)

Application robustness, UI accuracy, and professional engineering standards.

| Issue | Deduction | Notes |
|-------|-----------|-------|
| Critical failure | -10 to -15 | App crashes on launch or core interactions consistently fail. |
| UI/UX mismatch | -3 to -8 | Think of this like industry: the designer hands you a Figma, you implement it. Technical differences are fine, pixel-perfect is not required, but **all Figma elements must be present** and the page should look roughly the same at a glance. Missing a whole card/section from the Figma is a functional gap, not just a style issue. Minor layout or color differences are acceptable. Using different but functionally equivalent controls (e.g., list vs dropdown) is a minor deviation only. |
| Code fragility | -2 to -5 | Lack of basic error handling, improper state management, or fragile logic. If the student handles errors well in most places but misses one spot, lean toward -2 or even -1. |

### 3. Required Function (25 pts)

Completion and correctness of the assignment's core engineering objectives.

| Issue | Deduction | Notes |
|-------|-----------|-------|
| Missing feature | -5 to -10 per item | A required feature is not implemented at all. |
| Logic error | -3 to -10 | Feature exists but produces incorrect results or breaks expected flow. If the approach is sound but has a small bug, lean toward -3. |
| Hardcoding | -5 | Static values where dynamic computation/rendering is required. If hardcoding is limited to one minor case while the rest is dynamic, consider -1 to -2 instead. |

### 4. Timeliness (5 pts)

| Condition | Deduction |
|-----------|-----------|
| On time | 0 |
| Grace period | -1 to -2 |
| Late | -1 per day, up to -5 |

---

## III. Grading Guidelines

- **Demonstrated mastery > surface perfection.** A student who clearly understands
  React component composition but has a minor prop-naming inconsistency should not
  be penalized the same as one who doesn't understand components at all.
- **Context matters.** Look at the overall submission quality before deciding on
  individual deductions. A generally strong submission with one slip deserves
  leniency; a weak submission with the same slip does not.
- **Be consistent with prior assignments.** Reference previous HW grading to
  maintain fairness across the semester.
- **Feedback should be constructive.** Always explain *why* points were deducted
  and suggest how to improve.

---

## IV. Output Format

For each student, provide:
1. A list of concrete issues found
2. Point deductions aligned with this rubric
3. Clear, constructive feedback in English
