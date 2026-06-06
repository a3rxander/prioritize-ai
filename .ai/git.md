# Git Commit and Push Guidelines

You are an AI assistant helping with Git workflow for this repository.

Before creating any commit, always inspect the current repository state using:

```bash
git status
git diff
git diff --staged
```

## Main Rule

Do not mix unrelated changes in the same commit.

This repository is divided into main areas:

```txt
backend/   -> ASP.NET Core / C# backend
frontend/  -> React / TypeScript frontend
docs/      -> documentation
.ai/       -> AI assistant instructions and workflow guidelines
```

Create separate commits when changes belong to different areas.

For example:

* Backend changes should be committed separately from frontend changes.
* Documentation changes should be committed separately from code changes.
* AI instruction changes should be committed separately from application code.
* Do not combine formatting-only changes with feature or bug fix changes when they are unrelated.

## Commit Message Format

Use formal, clear commit messages following this format:

```txt
<type>(<scope>): <short description>
```

Examples:

```txt
feat(backend): add task entity
feat(frontend): create task form component
fix(backend): validate task estimated minutes
refactor(frontend): simplify task list rendering
docs(readme): update project structure
chore(ai): add git workflow guidelines
```

## Allowed Commit Types

Use one of these types:

```txt
feat      -> new feature
fix       -> bug fix
refactor  -> code change that does not add a feature or fix a bug
docs      -> documentation changes
chore     -> maintenance, configuration, tooling, setup
test      -> tests
style     -> formatting only, no logic changes
build     -> build system or dependency changes
ci        -> CI/CD changes
```

## Scope Rules

Use these scopes based on the affected area:

```txt
backend
frontend
docs
ai
root
database
auth
tasks
prioritization
azure
ci
```

Prefer the most specific scope when possible.

Examples:

```txt
feat(tasks): add task CRUD endpoints
feat(prioritization): add daily plan request model
chore(root): add gitignore
docs(readme): document MVP endpoints
chore(ai): add repository assistant instructions
```

## Commit Grouping Rules

When reviewing `git status`, group files by purpose.

### Backend commit

Use this when files changed under:

```txt
backend/
```

Example:

```txt
feat(backend): add task management API
```

### Frontend commit

Use this when files changed under:

```txt
frontend/
```

Example:

```txt
feat(frontend): add task creation page
```

### Documentation commit

Use this when files changed under:

```txt
README.md
docs/
```

Example:

```txt
docs(readme): add project overview
```

### AI instructions commit

Use this when files changed under:

```txt
.ai/
```

Example:

```txt
chore(ai): add git workflow instructions
```

### Root configuration commit

Use this when files changed at the repository root, such as:

```txt
.gitignore
.editorconfig
docker-compose.yml
```

Example:

```txt
chore(root): add repository configuration
```

## Staging Rules

Never run:

```bash
git add .
```

unless all modified files clearly belong to the same logical change.

Prefer staging files explicitly:

```bash
git add backend/src/PrioritizeAI.Domain/Entities/TaskItem.cs
git add backend/src/PrioritizeAI.Api/Controllers/TasksController.cs
```

Or stage by folder only when the entire folder belongs to the same change:

```bash
git add backend/
```

If backend and frontend files changed, create two separate commits:

```bash
git add backend/
git commit -m "feat(backend): add task CRUD API"

git add frontend/
git commit -m "feat(frontend): add task management UI"
```

## Push Rules

After commits are created, push to the current branch:

```bash
git push
```

If the branch has no upstream branch, use:

```bash
git push -u origin <branch-name>
```

Do not force push unless explicitly requested.

Never run:

```bash
git push --force
```

unless the user clearly asks for a forced push.

## Review Before Commit

Before committing, summarize:

1. Files changed
2. Suggested commit groups
3. Commit messages to use
4. Commands to run

Example response:

```txt
Detected changes:

Backend:
- Added TaskItem entity
- Added TaskStatus enum

Docs:
- Updated README project structure

Recommended commits:

1. feat(backend): add task domain model
2. docs(readme): update project structure
```

## Decision Rules

If a change affects both backend and frontend but belongs to one feature, still prefer separate commits unless the files must be committed together to keep the repository working.

Example:

```txt
feat(backend): add task CRUD endpoints
feat(frontend): connect task list to API
```

If a change is small and only updates documentation for a code change, it can be included in the same commit only if the documentation is directly tied to that code change.

Otherwise, keep documentation separate.

## Tone

Commit messages must be professional, short, and clear.

Avoid vague messages like:

```txt
update stuff
changes
fix
more work
final changes
```

Use meaningful messages like:

```txt
feat(tasks): add task creation endpoint
fix(frontend): handle empty task list
docs(readme): add local setup instructions
```
