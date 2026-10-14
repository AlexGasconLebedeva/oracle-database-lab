# Contributing Guidelines

## Branch naming convention

Create a separate branch for each issue or task. Use a prefix that describes the type of work, followed by the issue number and a short description.

Examples:

- `docs/1-contribution-guidelines`
- `feat/2-add-search`
- `fix/3-correct-readme`

## Commit message convention

Use Conventional Commits for commit messages.

The general format is:

`type: short description`

Common types include:

- `feat`: a new feature
- `fix`: a bug fix
- `docs`: documentation changes
- `test`: adding or updating tests
- `refactor`: code changes that do not add features or fix bugs

Examples:

- `docs: add contribution guidelines`
- `fix: correct installation instructions`
- `feat: add search functionality`

## Pull Request requirement

All changes must be submitted through a Pull Request. Do not push changes directly to `main`.

Before merging, the Pull Request must be reviewed and receive at least one approval. Address requested changes before merging.

### Optional scope

A scope can be added in parentheses after the commit type to identify the part of the project affected by the change. The scope is optional.

Examples:

- `docs(readme): clarify setup instructions`
- `feat(search): add search functionality`
- `fix: correct installation instructions`