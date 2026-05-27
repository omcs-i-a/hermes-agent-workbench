# Project Onboarding Checklist

Use this checklist when applying Hermes Agent to a new project repository.

## 1. Repository Basics

- [ ] Repository URL and local path identified.
- [ ] Default branch identified.
- [ ] README reviewed.
- [ ] License reviewed if relevant.
- [ ] Existing docs reviewed.

## 2. Stack Detection

- [ ] Main language(s).
- [ ] Frameworks.
- [ ] Package manager.
- [ ] Runtime version.
- [ ] Database or external services.
- [ ] Docker or compose files.

## 3. Commands

Identify exact commands:

- [ ] install:
- [ ] run/dev:
- [ ] test:
- [ ] lint:
- [ ] format:
- [ ] build:
- [ ] typecheck:

## 4. Project Structure

- [ ] Source directories.
- [ ] Test directories.
- [ ] Config directories.
- [ ] Documentation directories.
- [ ] Generated files to avoid.

## 5. Safety Boundaries

- [ ] Secrets locations identified and avoided.
- [ ] Production config identified and avoided.
- [ ] Destructive commands identified.
- [ ] External side effects identified.
- [ ] Approval-required operations documented.

## 6. Hermes Operating Rules

- [ ] Recommended skills.
- [ ] Recommended toolsets.
- [ ] Whether Codex/Claude Code/OpenCode should be used.
- [ ] Whether browser/computer_use is needed.
- [ ] Whether cron monitoring is useful.

## 7. Verification

- [ ] Baseline tests run or reason documented.
- [ ] Baseline build run or reason documented.
- [ ] Current git status checked.
- [ ] Known failures documented.

## 8. Handoff File

Create one of:

- [ ] `AGENTS.md`
- [ ] `HERMES.md`
- [ ] `docs/hermes.md`

It should include:

- project overview
- commands
- architecture notes
- safe operating rules
- do-not-touch files
- preferred workflow
- recommended skills
