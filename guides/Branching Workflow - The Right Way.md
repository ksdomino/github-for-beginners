Github Branches

Git doesn't work like "Save As..." on a Word doc; it works like a **Time Machine**.

Here is the breakdown of how to actually use this without losing your mind.

## 1. The "Branching" Workflow (The Right Way)

Don't think of branches as "Day 1, Day 2, Day 3." If you do that, you'll end up with a forest of branches and no idea where the "real" file is.

- **Main Branch:** This is your "Production" or "Final" version. It should always be the version you’d be happy to show a client or publish.
- **Feature Branch:** You create a branch when you have a **specific mission**.
  - *Mission:* "Update the pricing table."
  - *Branch Name:* `update-prices`
  - *Workflow:* Switch to branch -> Edit -> Commit -> Merge back to Main -> **Delete branch.**

------

## 2. When to Commit vs. When to Branch

This is the "trash to tidy" secret. You don't need a new branch for every minor edit.

| **Action** | **Why do it?**                                               | **Frequency**              |
| ---------- | ------------------------------------------------------------ | -------------------------- |
| **Commit** | To save a "checkpoint" so you can undo a mistake.            | Many times a day.          |
| **Branch** | To try something experimental or "big" without breaking your main version. | Once per "task" or "idea." |
| **Merge**  | To bring your finished, polished work back into your main folder. | When the task is done.     |

------

## 3. "The Magic Folder" (What actually happens on your Mac)

When you use GitHub Desktop to switch from `main` to `readme-edits`, Git literally **swaps the files** in your folder.

1. If you deleted a paragraph in the `readme-edits` branch and then switch back to `main` in GitHub Desktop...
2. **POOF.** That paragraph reappears in Typora instantly because GitHub Desktop replaced the file with the `main` version.

**This is why you don't need separate folders.** The `.git` folder keeps a database of all versions and "projects" them onto your folder based on which branch you select in the app.

------

## 4. How to keep track of where you are

Since Finder doesn't show the branch name, you have two choices to stay sane:

- **The "Desktop First" Rule:** Before you touch Typora or Photoshop, open GitHub Desktop. Look at the top. It says **Current Branch**. If it's not where you want to be, click it and switch.
- **The "Single Task" Rule:** Don't try to work on three branches at once. Finish one, merge it, delete it, and move back to `main`.

------

## 5. What about "Versions" (v0.1, v0.2)?

If you want to mark a specific point in time as "Version 1.0," don't use a branch. Use a Tag.

In GitHub (on the website), you can go to Releases and "Create a new release." You pick a commit, call it v1.0, and it stays there forever as a frozen snapshot, while your main branch keeps moving forward.

### Your next move:

Try this right now to see the "magic":

1. In GitHub Desktop, switch to your `readme-edits` branch.
2. Open the README in Typora and add the word **"WARLOCK"** in giant letters. Save it.
3. Go back to GitHub Desktop and **Switch to Main**.
4. Look at Typora. The word "WARLOCK" will disappear. Switch back to `readme-edits`—it's back.