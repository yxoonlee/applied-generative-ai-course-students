# Independent Project Review

- **Contributor**: yxoonlee
- **GitHub username**: yxoonlee
- **UTC review timestamp**: 2026-08-10T19:44:34Z
- **Reviewed commit**: `5e472bdd75823f342f9404c8ca70bc7771de2f83` (origin/main)

## Review focus

Whether limitations and the human-review-only boundary are consistent across the repository's documentation, automation, and contribution workflow.

## Files reviewed

- `README.md`
- `CONTRIBUTING.md`
- `AGENTS.md`
- `sims/README.md`
- `student-work/README.md`
- `setup/setup-guide.md`
- `assignments/project-1/brief.md`
- `.github/workflows/validate-student-pr.yml`
- `.github/workflows/auto-merge-sims.yml`
- `scripts/student-work-policy.mjs`
- `scripts/validate-student-pr.mjs`

## Verification commands executed

| Command | Result |
|---|---|
| `gh auth status` | PASS — authenticated as yxoonlee (keyring) |
| `gh api user` | PASS — login yxoonlee, id 313121101 |
| `gh repo view Alhabor/applied-generative-ai-course-students --json nameWithOwner,isPrivate,viewerPermission,defaultBranchRef` | PASS — public, READ permission, default branch main |
| `git status` | PASS — working tree clean on main |
| `git rev-parse HEAD` / `git rev-parse origin/main` | PASS — both at `5e472bdd` |
| `git diff --check` | PASS — no whitespace errors |
| `make check` | NOT AVAILABLE — no Makefile present in this repository |
| `python3 scripts/scan_secrets.py` | NOT AVAILABLE — no such script; repository uses Node.js-based validation via `scripts/validate-student-pr.mjs` instead |

## Observation

The repository enforces a consistent boundary across three layers: documentation (`AGENTS.md`, `CONTRIBUTING.md`), local validation (`scripts/validate-local-work.mjs`), and CI (`validate-student-pr.yml`). Each layer independently restricts student writes to `student-work/<login>/session-work/` and `student-work/<login>/submissions/`. The `auto-merge-sims.yml` workflow introduces a second boundary — single-folder `sims/<folder>/` changes merge automatically, while anything outside waits for instructor review. This two-tier design (student namespace for general work, sims namespace with auto-merge for Project 2) is consistent across all documentation surfaces and the CI code itself. However, the `sims/README.md` references a template at `resources/prd-template-icerynk-sim.md` that does not exist in this repository at the reviewed commit, which creates a gap in the otherwise self-contained submission instructions.

## Limitations of this review

- This review covers the repository as it existed at commit `5e472bdd`. Later commits may have addressed the noted gap.
- The `make check` and `scripts/scan_secrets.py` commands specified in the review procedure do not apply to this repository, as it uses a Node.js-based validation toolchain instead.
- The review did not execute the Node.js validation scripts locally, as they depend on a properly configured fork with upstream remote pointing to `clg236/applied-generative-ai-course-students`.
- No runtime testing of the CI workflows was performed.
- The review scope is limited to documentation consistency and boundary design; it does not assess course content, pedagogical structure, or assignment quality.

## Declaration

This contribution is an independent review record only. It does not modify source code, evaluation data, experimental results, presentation content, or project configuration.
