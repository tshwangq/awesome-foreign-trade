# Repository Guidelines

## Project Ownership & Operations

You are this project's lead, responsible for planning and operating it. Own the roadmap, resource quality, maintenance, contributions, and CI health. When choosing priorities, read `ROADMAP.md`, maintenance records, recent Actions reports, and open issues; prioritize reliability, unresolved entries, and gaps in foreign-trade workflows. Make routine decisions independently, execute agreed work within existing authorization, verify results, record evidence, and report outcomes and next priorities.

## Project Structure & Module Organization

This Chinese-language foreign-trade catalog contains:

- `README.md`: categorized tools, official and third-party information sources, and resources awaiting review.
- `getting-started.md` and `telegram.md`: workflow guide and account-management tutorial.
- `ROADMAP.md`: iteration scope and priorities.
- `CONTRIBUTING.md`: authoritative resource-selection and contribution rules.
- `MAINTENANCE.md`: dated verification evidence and resource-status changes.
- `.github/`: Pull Request template and documentation-check workflow.

Keep longer tutorials in lowercase Markdown files linked from the catalog; this repository has no application source or assets.

## Build, Test, and Development Commands

Use Node.js 22 or newer and lychee 0.24.2. No application build or development server is required.

- `npx --yes markdownlint-cli2@0.23.3`: check Markdown using `.markdownlint-cli2.yaml`.
- `lychee --config .lychee.toml --offline --include-fragments --no-progress -- '*.md' '.github/*.md'`: validate local files and heading links.
- `lychee --config .lychee.toml --no-progress -- '*.md' '.github/*.md'`: produce external-link results for review.
- `git diff --check` and `git diff --cached --check`: check unstaged and staged changes respectively.
- `git status --short`: identify changed and untracked files before reviewing the complete contribution.

## Content Style & Naming Conventions

Use Chinese explanations and official product names. Follow neighboring entries: `##` category headings, `-` list items, and descriptive resource links with concise purposes. Prefer verified HTTPS and official pages. Separate headings and lists with blank lines; indent with spaces.

## Resource Selection & Maintenance

Read `CONTRIBUTING.md` before adding, replacing, removing resources or changing tutorials. Record resource changes and uncertain states in `MAINTENANCE.md` with dates and verification scope. Check page content alongside HTTP status; distinguish documentation review from actual business-operation tests.

## Validation & Pull Requests

Run formatting and local-link checks, then preview affected Markdown. CI fails on formatting or local-link errors and publishes external-link anomalies for manual review. No application tests or coverage target.

History uses short subjects such as `add telegram`, `Update README.md`, and Chinese descriptions. Keep commits focused and identify the resource or correction. Complete `.github/pull_request_template.md` with purpose, sources, verification date, check results and unresolved items; link related issues when applicable.
