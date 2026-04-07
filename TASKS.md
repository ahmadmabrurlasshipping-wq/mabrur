# Proposed backlog tasks

## 1) Typo fix task
**Issue found:** Repository title in `README.md` is lowercase (`# mabrur`), which looks like an unintentional casing typo for a project name.

**Task:** Update the title to `# Mabrur` and make the short description a complete sentence.

**Acceptance criteria:**
- README heading is consistently title-cased.
- Description line ends with punctuation and reads clearly.

## 2) Bug fix task
**Issue found:** The repository currently has no executable usage/build/test instructions, so a first-time user cannot reliably reproduce expected behavior. This is an onboarding bug because it prevents successful setup.

**Task:** Add a minimal "Getting Started" section with exact commands for clone/setup/run (or explicitly state that code is not yet available and this is a docs-only scaffold).

**Acceptance criteria:**
- README includes step-by-step commands.
- A fresh user can follow the steps without guessing.

## 3) Code comment/documentation discrepancy task
**Issue found:** The README description (`vessel maintenance`) is too terse to explain scope and may conflict with future implementation intent because no modules/features are documented.

**Task:** Add a short "Scope" section clarifying what "vessel maintenance" covers (e.g., inspection scheduling, parts tracking, service logs) and what is out of scope.

**Acceptance criteria:**
- README contains explicit in-scope and out-of-scope bullets.
- Terminology is consistent throughout the README.

## 4) Test improvement task
**Issue found:** There are currently no tests or even a documented smoke-check workflow.

**Task:** Add an initial CI check and a minimal test/smoke command (language-appropriate once app code exists). Until then, add a placeholder check (e.g., markdown lint + link check) to prevent regressions in docs quality.

**Acceptance criteria:**
- CI runs at least one automated check on pull requests.
- A documented local command mirrors the CI check.
