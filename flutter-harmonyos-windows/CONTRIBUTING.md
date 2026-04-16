# Contributing

Thanks for contributing to `flutter-harmonyos-windows`.

## Scope
This repository contains a Cursor Skill for Flutter + HarmonyOS workflow on Windows.

Please keep contributions aligned with:
- Skill discoverability (clear trigger terms)
- Reproducibility (version matrix and validation steps)
- Practical troubleshooting (step-by-step fixes)

## How To Contribute

### 1) Open an issue first (recommended)
For major changes, open an issue before coding:
- Bug report
- Documentation improvement
- New feature proposal
- Compatibility update (new DevEco/SDK/Flutter versions)

### 2) Fork and create a branch
Use focused branch names:
- `docs/update-readme-smoke-test`
- `fix/hdc-troubleshooting-flow`
- `feat/add-macos-variant`

### 3) Make minimal, targeted changes
Keep PRs small and scoped. Avoid mixing unrelated edits.

### 4) Verify before PR
Checklist:
- [ ] `SKILL.md` still concise and actionable
- [ ] Trigger terms are specific and relevant
- [ ] Commands are executable and tested where possible
- [ ] Paths use `/` style
- [ ] Cross-file consistency (`SKILL.md`, `README.md`, `reference.md`, `troubleshooting.md`)
- [ ] `CHANGELOG.md` updated under `Unreleased`

Minimal local validation commands (smoke test):
```bash
flutter --version
flutter doctor -v
flutter create --platforms ohos smoke_demo
cd smoke_demo
flutter build app --release
```

Expected:
- `flutter doctor -v` has no blocking errors
- Unsigned `.hap` is generated under `ohos/build/outputs/default`

### 5) Open pull request
PR should include:
- What changed
- Why it changed
- How it was validated
- Any known limitations

## Issue Templates (Suggested)

### Bug report
- Environment (Windows version, DevEco version, Flutter branch)
- Exact command that failed
- Full error output
- What you expected
- What actually happened

### Compatibility update
- Previous known-good version
- New tested version
- Breaking differences
- Required docs updates

## Writing Guidelines
- Keep instructions direct and verifiable
- Prefer commands + expected results over long explanations
- Put deep details in `reference.md`
- Keep `SKILL.md` focused on execution flow

## Code of Conduct
Be respectful, constructive, and specific in feedback.
