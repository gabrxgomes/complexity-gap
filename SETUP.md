# SETUP.md — Step-by-step guide

## 1. Create the repository on GitHub

1. Go to https://github.com/new
2. Name: `complexity-gap`
3. Visibility: **Public** (required for free GitHub Pages)
4. Do NOT initialize with a README (you will push the structure manually)
5. Click "Create repository"

---

## 2. Clone and push the structure

```bash
git clone https://github.com/gabrxgomes/complexity-gap
cd complexity-gap

git add .
git commit -m "feat: initial project structure and blog setup"
git push origin main
```

---

## 3. Enable GitHub Pages

1. In the repository, go to **Settings** → **Pages**
2. Under "Source", select **GitHub Actions**
3. Save

The blog deploys automatically on every push to `main`.
URL: `https://gabrxgomes.github.io/complexity-gap`

---

## 4. Run the blog locally

```bash
pip install -r requirements-docs.txt
mkdocs serve
```

Access `http://127.0.0.1:8000` to preview before pushing.

---

## 5. Recommended commit structure

Each research step becomes a descriptive commit:

```
feat: implement Erdos-Renyi graph generator
feat: BFS with metrics instrumentation
feat: experiment pipeline for sparse graphs
data: BFS x grid 1000 nodes results
docs: gap analysis BFS vs theory
```

This creates a public research diary with timestamps, citable in the paper.

---

## 6. If push is rejected (remote ahead)

```bash
git pull origin main --rebase
git push origin main
```

---

## 7. Verify deployment

After pushing, go to **Actions** on GitHub and follow the `Deploy MkDocs to GitHub Pages` workflow.
The blog will be live in ~2 minutes.
