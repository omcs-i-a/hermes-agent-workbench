# Tooling Catalog

This document summarizes the Hermes tools and skills currently relevant to this AI Agent research workbench.

## Enabled Toolsets

The following toolsets are enabled for the current CLI environment.

### `web`

Purpose: search and extract web content.

Use for:

- Literature and ecosystem research.
- Documentation lookup.
- Blog and announcement discovery.
- GitHub or package information gathering when a browser UI is not required.

Prefer `web` over `browser` for static pages, plain text, JSON, Markdown, and simple documentation lookup.

### `browser`

Purpose: automate a controlled browser.

Use for:

- Dynamic websites.
- Web application QA.
- Login-gated research where the user has already authorized the session.
- Clicking, typing, scrolling, screenshots, and JavaScript console inspection.
- Inspecting visual or DOM state.

Basic workflow:

1. Navigate to a URL.
2. Capture a snapshot.
3. Click/type/press using element references.
4. Re-capture or inspect console output.
5. Record sources and observations.

Avoid using `browser` when a simpler web fetch or terminal command is enough.

### `computer_use`

Purpose: operate macOS GUI applications in the background.

Use for:

- Native macOS apps.
- GUI-only workflows.
- Safari/Finder/app automation when `browser` is insufficient.
- Screen-grounded agent research.

Operating rules:

- Capture first, then act on element indices.
- Prefer element references over coordinates.
- Re-capture after state-changing actions.
- Do not raise windows unless the user explicitly asks.
- Do not interact with permission dialogs, password prompts, payment flows, or 2FA challenges without explicit approval.
- Do not type secrets.

Prefer `browser` for web tasks and `file`/`terminal` for file or shell tasks.

### `terminal`

Purpose: run shell commands, git, CLI tools, tests, and local scripts.

Use for:

- Git status, branches, diffs, and remotes.
- Running `hermes`, `gh`, `codex`, test commands, and package managers.
- Starting tracked background processes.
- Running coding agents in worktrees.

Rules:

- Use foreground commands for short tasks.
- Use `background=true` with `notify_on_complete=true` for long bounded jobs.
- Use `pty=true` for interactive CLIs such as Codex.
- Use file tools instead of shell commands for reading/writing/searching files when possible.

### `file`

Purpose: read, write, search, and patch repository files.

Use for:

- README and documentation editing.
- Prompt and agent spec maintenance.
- Searching project content.
- Targeted file patches.

Rules:

- Use `read_file` instead of `cat`.
- Use `search_files` instead of `grep`, `rg`, `find`, or `ls`.
- Use `write_file` for new full files.
- Use `patch` for targeted changes.

### `code_execution`

Purpose: run small Python programs and coordinate multiple tool calls with processing logic.

Use for:

- Transforming data.
- Summarizing file inventories.
- Parsing JSON/CSV.
- Running small deterministic analysis scripts.

### `vision`

Purpose: analyze images and screenshots.

Use for:

- Browser screenshots.
- GUI captures.
- Diagrams and charts in papers or docs.
- UI state verification.

### `image_gen`

Purpose: generate images.

Use for:

- Optional diagrams or visual assets.
- Concept illustrations.

Not required for the minimal research workflow.

### `skills`

Purpose: load and manage reusable task procedures.

Use for:

- Hermes configuration knowledge.
- Research procedures.
- Coding-agent delegation procedures.
- Skill authoring and maintenance.

Important skills should be loaded before acting, especially when configuring Hermes or using Codex.

### `todo`

Purpose: track in-session work.

Use for:

- Multi-step research.
- Documentation scaffold work.
- Implementation/review workflows.

### `memory`

Purpose: persist stable user or environment facts.

Use for:

- Durable preferences.
- Stable environment conventions.
- Tool quirks that will remain useful.

Do not use memory for temporary task progress, report content, PR numbers, commit SHAs, or stale facts.

### `session_search`

Purpose: search prior Hermes sessions.

Use for:

- Recovering prior design decisions.
- Finding previous research discussions.
- Continuing work without asking the user to repeat context.

### `clarify`

Purpose: ask the user a targeted question when required information is not retrievable.

Use sparingly. Prefer acting on obvious defaults when safe.

### `delegation`

Purpose: spawn subagents for isolated subtasks.

Use for:

- Parallel research.
- Independent source gathering.
- Reviewer passes.
- Coding task review.

Patterns:

- Paper scout.
- Framework scout.
- Benchmark scout.
- Source quality reviewer.
- Report consistency reviewer.

Subagents do not inherit full conversation memory, so pass complete context.

### `cronjob`

Purpose: schedule durable future agent runs.

Use for:

- Daily or weekly research briefings.
- arXiv monitoring.
- Blog/RSS monitoring.
- GitHub repository or issue monitoring.
- Chained collection and synthesis jobs.

Rules:

- Prompts must be self-contained.
- Cron jobs cannot ask clarifying questions.
- Use `skills` to preload relevant procedures.
- Use `script` for deterministic data collection.
- Use `no_agent=true` only when script output is the exact desired message.
- Use `context_from` to chain collector and synthesizer jobs.

### `messaging`

Purpose: send messages to configured platforms.

Use for:

- Research briefings.
- Scheduled alerts.
- Sharing reports to connected channels.

## Disabled Toolsets

Currently disabled in the CLI environment:

- `video`
- `video_gen`
- `x_search`
- `moa`
- `homeassistant`
- `spotify`
- `yuanbao`

Enable only when a research workflow explicitly needs them.

## High-Value Skills for This Workbench

### Hermes and autonomous-agent skills

- `hermes-agent`: Hermes setup, configuration, tools, skills, cron, gateway, MCP, profiles, and contributor notes.
- `codex`: delegate coding work to OpenAI Codex CLI.
- `kanban-codex-lane`: use Codex as an isolated implementation lane while Hermes remains lifecycle owner.
- `claude-code`: delegate coding work to Claude Code CLI.
- `opencode`: delegate coding work to OpenCode CLI.

### Planning and development skills

- `writing-plans`: create detailed implementation plans.
- `subagent-driven-development`: implement plans using fresh subagents and two-stage review.
- `test-driven-development`: enforce red-green-refactor when writing code.
- `systematic-debugging`: root-cause debugging workflow.
- `requesting-code-review`: pre-commit review workflow.
- `spike`: run throwaway experiments to validate an idea.

### Research skills

- `arxiv`: search arXiv papers.
- `blogwatcher`: monitor blogs and RSS/Atom feeds.
- `llm-wiki`: build and query a local LLM knowledge base.
- `polymarket`: query prediction market data.
- `research-paper-writing`: ML paper writing workflow.

### GitHub skills

- `github-repo-management`: clone, create, fork, and manage repositories.
- `github-pr-workflow`: branch, commit, open PRs, check CI, merge.
- `github-code-review`: review pull requests.
- `github-issues`: create and triage issues.
- `codebase-inspection`: inspect codebase size and language composition.

### MCP and integration skills

- `native-mcp`: connect MCP servers and register MCP tools.
- `google-workspace`, `notion`, `obsidian`: optional knowledge-management integrations.

### Desktop/browser research skills

- `macos-computer-use`: operate macOS apps in the background.
- `dogfood`: exploratory QA of web apps.

## Codex Role Summary

Use Codex as an implementation worker, not as the source of truth.

- Hermes owns planning, scope, review, verification, and final acceptance.
- Codex can generate a candidate diff.
- Run Codex in a git repository, preferably an isolated worktree for non-trivial changes.
- Use `pty=true` for Codex CLI.
- Use `codex exec` for bounded one-shot work.
- Review the diff and rerun tests from Hermes before accepting any Codex output.

## Minimal Tooling for AI Research Agent

Required:

- `web`
- `file`
- `terminal`
- `skills`
- `delegation`
- `cronjob`
- `session_search`

Recommended:

- `browser`
- `vision`
- `code_execution`
- `arxiv`
- `blogwatcher`
- `github-*` skills

Optional for advanced experiments:

- `computer_use`
- `native-mcp`
- `codex`, `claude-code`, `opencode`
- `evaluating-llms-harness`
- `weights-and-biases`
