# Contributing to ML_Collage_Project

How our team works in this repo. Following these steps keeps `main` working and shows every member's individual contributions in the commit history.

## Ground rules

- `main` always works. **Nobody pushes directly to `main`.**
- One task = one branch = one pull request (PR).
- Every PR is reviewed by someone who did not write it.
- Commit under your own GitHub account, early and often.
- Only edit files you own. If you need a change in someone else's file, ask them or open an issue.

## One-time setup

```bash
git clone https://github.com/<owner>/ML_Collage_Project.git
cd ML_Collage_Project
git config user.name "Your Name"
git config user.email "the-email-on-your-github-account"
python -m venv .venv
# activate the environment, then:
pip install -r requirements.txt
```

## Workflow for every task

1. **Sync:** `git checkout main` then `git pull`
2. **Branch:** `git checkout -b part-b-hog-features`
3. **Work and commit often:**
   `git add <specific files>` then `git commit -m "part-b: add HOG feature extraction"`
4. **Push:** `git push -u origin part-b-hog-features` (first time), then `git push`
5. **Open a PR** on GitHub: base = `main`, compare = your branch. Describe what changed, why, and how to run it. Request your reviewer.
6. **Address feedback** by pushing more commits to the same branch.
7. **Merge:** once approved, click **Merge pull request** (use a regular merge, not "Squash and merge", so individual commits stay visible), then delete the branch.
8. **Clean up:** `git checkout main`, `git pull`, `git branch -d part-b-hog-features`

## Branch names

Use `<area>-<short-task>`:

- `part-a-...`, `part-b-...`, `part-c-...`
- `gui-...`, `bonus-...`, `docs-...`

Keep branches short-lived (a few days) and run `git pull` before pushing.

## Commit messages

Format: `part-x: what changed`

- `part-a: handle missing values in price column`
- `part-c: tune C for linear SVM on validation set`
- `gui: add image upload tab`

One logical change per commit.

## What not to commit

- Datasets (put a download link in the README instead)
- Large model files (GitHub rejects files over 100 MB; a saved KNN model stores its training data, so check its size)
- `__pycache__/`, `.ipynb_checkpoints/`, `.venv/`
- Passwords, tokens, or personal data

## Notebooks

- Each notebook has **one owner**. Split by task (for example `01_preprocessing.ipynb` and `02_models.ipynb`) instead of editing the same file.
- Before committing, run **Restart & Run All** and confirm it finishes without errors.
- Clear outputs before committing if the team agreed to (this keeps diffs small).

## PR checklist (copy into the PR description)

- [ ] Notebook runs top to bottom with no errors
- [ ] `random_state` is fixed in every split and model
- [ ] Scalers, vectorizers, and PCA are fitted on training data only
- [ ] Hyperparameters were chosen on the validation set (or cross-validation); the test set is used once, at the end
- [ ] Every preprocessing step has a short markdown note explaining why it was applied
- [ ] No datasets, caches, or large files were committed
- [ ] README is updated if the run steps changed

## Reviewing a PR

1. Open **Files changed** and read the code.
2. Ask yourself: *could I explain this line in the discussion?* If not, ask the author.
3. Comment on specific lines, then **Approve** or **Request changes**.

Review rotation: Part A PRs are reviewed by the Part B pair, Part B by the Part C pair, and Part C by the Part A pair. GUI and README PRs are reviewed by any member who did not write them.

## Merge conflicts

Git marks conflicts in the file with `<<<<<<<`, `=======`, and `>>>>>>>`. Open the file, keep the correct version, delete the markers, then `git add` and `git commit`. Resolve it together with the other author rather than guessing.

## Team leader checks

- Look at open PRs every day or two so reviews don't pile up.
- Check **Insights → Contributors** weekly to make sure every member is committing.
- Before submission: do a fresh clone into a new environment, confirm the README steps work, and tag the final version (for example `v1.0`).
