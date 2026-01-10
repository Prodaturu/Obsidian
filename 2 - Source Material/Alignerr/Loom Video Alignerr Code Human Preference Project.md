# Alignerr Code Human Preference Project

## Big Picture

You are participating in a **Code Human Preference (HFI)** evaluation project.

Your role is to **evaluate AI-generated code changes**, not just write code.
You will:

* Prompt two AI models
* Compare their outputs (Model A vs Model B)
* Explain *why* one is better
* Submit structured feedback and artifacts

---

## Step-by-Step Instructions

### 1. Access Your Mailbox

* Click **Access Mailbox** in the project UI
* Copy the **special Alignerr email address** shown at the top
* You will use this email to log into the feedback portal

---

### 2. Read the Project Instructions

Go to **Instructions** and read carefully.
Focus on:

* [[CLI installation Code Human Preference Project|CLI installation]]
* Prompting guidelines
* Rationale & rating rules
* Submission process

You will return to this document often.

---

### 3. Install the Cloud HFI CLI

1. Go to the **Feedback Portal**
2. Log in using your special Alignerr email
3. Get the login code from your mailbox
4. Download the correct binary:

   * Mac → Darwin
   * Linux → Linux x64
   * Windows → WSL required
5. Move it to a global bin directory, e.g.:

   ```bash
   ~/.local/bin
   ```
6. Make it executable:

   ```bash
   chmod +x cloud-hfi
   ```

Check Discord to ensure your version is up to date.

---

### 4. Choose a Codebase (Repo)

Your repo must:

* Be a git repository
* Match your assigned language
* Be open source
* Have build/run instructions
* Be reasonably high quality (but imperfect)

Before starting:

* Browse the repo
* Try running examples or tests
* Identify real problems

---

### 5. Clone and Open the Repo

```bash
git clone <repo-url>
cd <repo>
cloud-hfi --vscode
```

This opens:

* Your browser
* Two VS Code windows

Each VS Code window is a **worktree**:

* Worktree A → Model A
* Worktree B → Model B

---

### 6. Turn 1 – Write Your First Prompt

This is the **most important turn**.

Your prompt should:

* Describe issues from a **user perspective**
* Explain what is broken, confusing, or missing
* Mention specific observations
* Avoid prescribing exact solutions

Good example:

> The examples do not run correctly, rely on magic numbers, and do not explain how users should interact with the system.

Bad example:

> Clean up the code and improve naming.

Paste the prompt into Cloud HFI and press Enter.
Wait until **both models finish**.

---

### 7. Evaluate Model A vs Model B

For each model:

* Inspect code changes
* Run examples/tests if possible
* Check if original issues were *actually fixed*

Watch out for:

* Superficial fixes
* Breaking abstractions
* Hallucinated features or fake roadmaps

---

### 8. Write Your Rationale

You must write:

* Pros of Model A
* Cons of Model A
* Pros of Model B
* Cons of Model B
* Overall preference justification

Rules:

* Each point must be atomic
* Do not mix models in one bullet
* Base claims on observed behavior
* Rationale must match your ratings

---

### 9. Give Ratings

Rate categories such as:

* Overall quality
* Modularity
* Documentation
* Interface design
* Readiness to merge

Tips:

* Use the ❓ tooltips
* Let your rationale guide scores
* Choose A or B honestly (this determines the next turn)

Submit feedback for **Turn 1**.

---

### 10. Upload the Preferred Codebase

After Turn 1:

1. Copy the repo to `/tmp`
2. Remove unnecessary folders (venv, node_modules, etc.)
3. Create a tarball:

   ```bash
   tar cf traffic-simulator.tar ./traffic-simulator
   ```
4. Upload the tarball to the **Google submission form**
5. Provide:

   * Discord username
   * UUID
   * Initial git commit hash

---

### 11. Turn 2 (and Possibly Turn 3)

Now write a **more specific and critical prompt**:

* Target concrete failures from Turn 1
* Be narrower and more prescriptive

Repeat:

* Evaluate both models
* Write rationale
* Rate
* Submit feedback

Most submissions are **2 turns**, sometimes 3.

---

### 12. Final Submission

At the end:

* Generate a diff from the original commit
* Apply it to a clean clone to confirm it works
* Upload:

  * Diff file
  * Time spent
  * Number of turns
  * Final ratings

Submit the form.

---

## One-Sentence Summary

You prompt AI models to improve a real codebase, rigorously compare their changes, explain your reasoning, and submit structured feedback — **not just code**.
 