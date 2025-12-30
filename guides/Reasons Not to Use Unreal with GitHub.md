# Reasons Not to Use Unreal with GitHub

### 1. The "Binary Bloat" Problem

Git was designed to track lines of text. Unreal projects are made of **Binaries** (`.uasset`, `.umap`).

- **Storage Inefficiency:** Every time you save a 50MB character blueprint, Git doesn't just save the change; it saves a whole new 50MB file in your hidden `.git` folder. Your local project size will balloon exponentially, slowing down every single Git operation (Status, Commit, Push).
- **The "LFS" Tax:** To avoid the 100MB file limit, you must use Git LFS. GitHub’s free tier for LFS is extremely restrictive (usually 1GB). Once you hit that, your team cannot push or pull until you start paying monthly for data packs.

### 2. Lack of Native "Exclusive Checkout"

In professional game dev, you need to "Lock" a file so no one else can touch it while you are working.

- **The Workflow Gap:** GitHub is designed for "decentralized" work—everyone changes everything and merges later. You **cannot** merge two people's changes to the same Blueprint.
- **Invisible Collisions:** Without a native "Lock" icon in the Unreal Editor (which GitHub lacks by default), two teammates will inevitably spend 4 hours working on the same Enemy AI, only for one person's work to be completely overwritten during the next "Push."

### 3. High "Git-Fried" Risk (Corruption)

- **Partial Pushes:** Because Unreal files are so large, GitHub pushes often time out or fail mid-way. This can leave your repository in a "detached" or corrupted state that requires command-line surgery to fix.
- **Index Bloat:** As the project grows to 50GB+, GitHub Desktop and other Git GUI tools often hang or crash trying to calculate the "Diff" for thousands of binary files.

### 4. Poor Editor Integration

- **Context Switching:** To use GitHub effectively, developers have to constantly Alt-Tab out of Unreal to use GitHub Desktop.
- **Status Blindness:** You can't easily see inside the Unreal Content Browser which files are "Modified" or "Added" by your teammates in real-time.

### 5. Branching is a Trap

- Branching is Git's "Killer Feature," but it is a **nightmare** for Unreal. Merging a "Feature Branch" back into "Main" when that branch contains 200 binary assets usually results in dozens of "Merge Conflicts" that cannot be resolved automatically. You end up having to manually pick "Theirs" or "Mine" for every single asset.

------

## The Professional Alternatives

If you are moving away from GitHub, these are the two paths used by the industry:

### 1. Perforce (P4V) — *The Industry Standard*

- **Why:** It is a "Centralized" system. It doesn't download the whole history to your machine (saving disk space).
- **The "Killer Feature":** **Exclusive Checkout.** When you double-click a file in Unreal, it "Checks Out" the file in Perforce. Your teammates see a red checkmark in their editor and literally **cannot** save changes to that file until you submit it.
- **Cost:** Free for up to 5 users. Requires a dedicated server (you can host one on a cheap cloud provider for ~$10/month).

### 2. SVN (Subversion) — *The Indie Alternative*

- **Why:** Like Perforce, it handles binaries much better than Git and supports file locking.
- **The "Killer Feature":** It’s much easier to set up than Perforce and has great integration with the Unreal Editor. It's an excellent middle ground for teams who find Perforce too complex but GitHub too messy.

### 3. Diversion — *The Modern Challenger*

- **Why:** A newer version control system specifically built for game engines. It feels like Git but handles large assets and cloud storage natively without the "LFS" headaches.