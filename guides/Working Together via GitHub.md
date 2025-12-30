# Working Together via GitHub

This section will show you how to add your work to a project using GitHub Desktop. We use a "Branching Workflow," ie: *We work in our own branches so we don't accidentally break the main project.*

------

## 1. The "Daily Loop" (Your Standard Routine)

### 🏁 Step A: Start Fresh

Before anything, make sure you have the latest version of the project:

1. **Open GitHub Desktop.**
2. Click the **Fetch Origin** button at the top.
3. **Switch to `main`:** In the branch selector, make sure you are on `main`.
4. **Pull:** If the button says **Pull Origin**, click it.
5. **New Branch:** Click the branch button → **New Branch**. Give it a simple name like `update-tutorial` or `fix-typo`.

### ✍️ Step B: Do Your Work

1. **Edit your files:** Use whatever editor works for you.

2. **Commit (Save Checkpoints):** In GitHub Desktop, you’ll see your changes on the left. Write a short summary (e.g., "Fixed a typo") and click **Commit to [your branch]**.

   **NOTE: IT WONT LET YOU COMMIT UNLESS YOU PUT SOMETHING IN THE SUMMARY-REQUIRED BOX.**
   *(The 2nd box (Description) may be optional - if the commit button is still greyed out then put something in there too.)*

   - *Tip: Do this often! It's like hitting 'Save' in a video game.*

3. **Push:** Click **Push Origin**. This sends your work from your computer up to GitHub.com.

### 🏁 Step C: The "Finished" Line

1. **Open a Pull Request (PR):**
   - On GitHub.com, you’ll see a yellow bar asking if you want to **Compare & pull request** — click it.
   - Or in GitHub Desktop, click **Create Pull Request**.
2. **Wait for Review:** After it's been reviewed, the admin will merge it and possibly message you if needed.
3. **Merge & Delete:** Once the admin merges it, it becomes part of `main`. You can now delete your branch.

------

## 2. What if the Admin is slow to merge?

If your PR is open but still waiting, do this once a day (or whenever `main` changes a lot) to keep your branch fresh:

1. **Switch to `main` → Fetch & Pull:** Click **Fetch Origin**, then **Pull Origin** (if available).
2. **Switch to your branch:** Go back to the task you are working on.
3. **Update from `main`:**
   - In the top menu, go to **Branch → Merge into current branch…**
   - Choose `main`
   - (Sometimes you’ll also see **Update from main** — same idea)
4. **Fix conflicts if they pop up**
5. **Push:** Click **Push Origin** to send the update to GitHub.

> **Why do this?** This prevents “merge conflicts” (when two people change the same line and GitHub gets confused). It keeps your work compatible with everyone else’s.

------

## 3. Simple Rules for a Happy Team

- **One Task, One Branch:** Don’t try to fix the whole thing in one branch. Keep it small — it’s easier to review.
- **Don't be afraid of "Drafts":** You can set your Pull Request to **Draft** to say: “I’m still working on this, but you can see my progress.”
- **Start every new task from `main`:** (Step A first, every time.)
- **If you see conflicts:** report it immediately — ask the admin/teammate and paste the exact error text.

### Tiny wording tweak (optional but clearer)

- Instead of “private spaces”, you can say **“your own branch”** (same meaning, more GitHub-y).