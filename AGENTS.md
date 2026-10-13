# Repository Guidelines

## Project Structure & Module Organization

This repository is a Chinese-language catalog of foreign-trade resources.

- `README.md`: categorized tools, official and third-party information sources, and resources awaiting review.
- `telegram.md`: supplementary account-management tutorial.
- `CONTRIBUTING.md`: authoritative resource-selection and contribution rules.
- `MAINTENANCE.md`: dated verification evidence and resource-status changes.
- `.github/`: Pull Request template and documentation-check workflow.

There is no application source, build output, or asset directory. Put longer tutorials in lowercase Markdown filenames and link them from the catalog.

## Build, Test, and Development Commands

Use Node.js 22 or newer and lychee 0.24.2. No application build or development server is required.

- `npx --yes markdownlint-cli2@0.23.3`: check Markdown using `.markdownlint-cli2.yaml`.
- `lychee --config .lychee.toml --offline --include-fragments --no-progress -- '*.md' '.github/*.md'`: validate local files and heading links.
- `lychee --config .lychee.toml --no-progress -- '*.md' '.github/*.md'`: produce external-link results for review.
- `git diff --check` and `git diff --cached --check`: check unstaged and staged changes respectively.
- `git status --short`: identify changed and untracked files before reviewing the complete contribution.

## Content Style & Naming Conventions

Use Chinese explanations, official product names, `##` category headings, `-` list items, and descriptive Markdown links. Match neighboring entries: a resource link followed by a brief explanation of its foreign-trade use. Prefer verified HTTPS and official product pages. Separate headings and lists with blank lines; use spaces for indentation. Markdown linting allows long paragraphs and URLs.

## Resource Selection & Maintenance

Read `CONTRIBUTING.md` before adding, replacing, removing resources or changing tutorials. Follow its selection, evidence, and review rules. Record removals, migrations and uncertain product states in `MAINTENANCE.md` with dates and verification scope. Check final page content as well as HTTP status. Distinguish documentation review from actual login or business-operation testing.

## Validation & Pull Requests

Run formatting and local-link checks, then preview affected Markdown. CI fails on formatting or local-link errors and publishes external-link anomalies for manual review. There is no application test framework or coverage target.

History uses short subjects such as `add telegram`, `Update README.md`, and Chinese descriptions. Keep commits focused and identify the resource or correction. Complete `.github/pull_request_template.md` with purpose, sources, verification date, check results and unresolved items; link related issues when applicable.
