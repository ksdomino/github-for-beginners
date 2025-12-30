## Terminology & Naming Conventions

- **Local Repo** = one project folder with a hidden `.git` database that stores history/branches.
- **Working folder** (the files you edit in Finder/Typora). You won't see branches but when you choose a branch in github desktop, that branches version of files will be shown in Finder.  **This is git magic!**
- **Commit** = checkpoint. After making changes to files, you click commit to commit those changes to the repo, most of the time this will be in the main branch for solo workers or in a branch if you're working as a collaborator. more about branches later.
- **Branch** = a temporary lane to work on one change without touching `main`.
- **Push/Pull** = upload/download commits to/from GitHub.com.

------

## Folder + naming convention (simple + scalable)

On your Mac:

- `Global/GitHub/<ProjectName>/` (one folder per repo)

Inside repo:

- `/docs` (markdown + guides)
- `/assets` (images, logos, reference)
- `/exports` (PDFs/PNGs for review)
- `/src` (source files, usually for code)

------

## Solo workflow (fastest, least confusion)

Use branches only when you’re trying something risky/experimental.

**Daily loop**

1. Open GitHub Desktop
2. Confirm **Current Branch = main**
3. Work in Typora/InDesign
4. Commit checkpoints as you go:
   - “Update intro”
   - “Fix pricing table”
   - “Add screenshots”
5. Push when you want it on GitHub.com

------

## Team workflow

### Roles

- **main** = “approved / client-safe”
- Everyone works in **task branches**
- Changes arrive via **Pull Requests** (PRs)

### Branch naming (boring = good)

- `docs-readme-update`
- `flyer-price-change`
- `indesign-layout-v2`
- `fix-typos`

### The “one task per branch” rule

A branch should answer: “What change is this branch for?”
If it can’t be said in one line, split it.

------

## Standard collaborator loop (GitHub Desktop only)

### Start work (every time)

1. Open GitHub Desktop
2. **Fetch origin**
3. Switch to `main`
4. **Pull** (if available)
5. Create new branch from `main`

### Do work

1. Edit files normally
2. Commit as checkpoints (multiple commits is fine)
3. Push branch

### Review + merge

1. Open PR on GitHub.com (base: `main`, compare: your branch)
2. Reviewer checks:

- Markdown diffs
- Exported PDFs/PNGs for binary changes

1. Merge PR
2. Delete branch

### After merge (everyone)

1. Switch to `main`
2. Pull

------

## How to handle binary/design files so PRs are reviewable

For INDD/PSD/AI changes, make your PR contain:

- The **source file** update (INDD/PSD)
- A fresh **export** (PDF/PNG) inside `/exports`

Commit message examples:

- “Update layout (INDD) + export PDF”
- “Revise cover typography + export PNG”

That way reviewers don’t have to download and open InDesign to understand the change.

------

## What `.git` really stores (keep this short in your guide)

- It’s not “a hash file”. It’s a mini database:
  - commits (snapshots)
  - branches (pointers to commits)
  - file contents for each commit
- For text, Git can show diffs line-by-line.
- For binaries, Git mostly tracks “this file changed” (and stores the new version).

You can include this as a 2–3 bullet “FYI” section, but it’s not required for day-to-day use.

------

## Commit messages your team can follow (copy/paste rules)

Good format:

- Verb + thing:
  - “Add class timetable”
  - “Fix pricing typo”
  - “Update flyer date”
  - “Replace hero image”
    Avoid:
- “update”
- “changes”
- “final final v7”

------

## Minimal “workflow pages” to include in your guidebook

1. Create local repo (Desktop)
2. Publish repo (Desktop)
3. Clone repo (Desktop)
4. The daily routine (Fetch → Pull → Branch → Commit → Push)
5. Pull Requests + review checklist
6. Handling design files (exports rule)
7. Common mistakes + fixes
   - forgot to pull
   - edited on wrong branch
   - merge conflict basics (Desktop)

------

## Your current setup (hello-world2) — what to do next

- Keep using it as your training sandbox.
- Practice:
  - create branch → edit README in Typora → commit → push → PR → merge → delete branch

Once that feels boring, you’re ready to teach it.

If you want, paste your current table-of-contents for the InDesign guide and I’ll rewrite it into a clean “training manual” structure with the exact click-path steps for GitHub Desktop (no terminal).