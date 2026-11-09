# Repository Guidelines

## Project Structure & Module Organization

This repository is currently an empty project scaffold: no application code, tests, assets, or dependency manifests have been committed. Keep this guide aligned with the implementation as it develops.

When adding the initial application, group source code in `src/`, automated tests in `tests/` or alongside their modules, and static assets in `public/` or `assets/`, as appropriate for the chosen framework. Document the actual layout in `README.md`; avoid creating empty directories solely to match this suggestion.

## Build, Test, and Development Commands

No build system, package manager, or development commands are configured yet. Add reproducible setup, development, build, and test commands to `README.md` when introducing tooling. For example, if npm is selected, define and document `npm run dev`, `npm run build`, and `npm test` before recommending them to contributors. Commit the selected package manager's lockfile.

## Coding Style & Naming Conventions

Follow the conventions of the selected language and framework. Use consistent indentation, descriptive names, and small modules with clear responsibilities. Prefer names that reflect the domain, such as `ingredients`, `recipes`, and `inventory`. Introduce a formatter and linter with the first implementation, commit their configuration, and document how to run them.

## Testing Guidelines

No test framework or coverage threshold is established. Add tests for new behavior and regression tests for fixes. Use descriptive test names that state the scenario and expected result. Keep tests deterministic and document required fixtures or services.

## Commit & Pull Request Guidelines

There is no commit history from which to infer conventions. Use concise, imperative commit subjects, such as `Add ingredient inventory model`. Keep changes focused. Pull requests should explain the problem, summarize the solution, link relevant issues, and report validation performed. Include screenshots for visible interface changes and explicitly identify checks that could not be run.

## Security & Configuration

Never commit credentials or local secrets. If configuration is introduced, provide sanitized examples and document required environment variables.
