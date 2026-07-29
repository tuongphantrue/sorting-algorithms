# sort://lab

A single-page, dependency-free visualizer for six classic sorting algorithms — Bubble, Selection, Insertion, Merge, Quick, and Heap sort. Bars animate in real time, comparisons/swaps are counted, and a pseudocode panel highlights the exact line currently executing.

Everything lives in one file (`index.html`), so there's no build step and no npm install.

## Run it locally

Just open `index.html` in any browser.

## Publish it on GitHub Pages

1. Create a new repository on GitHub (e.g. `sort-lab`).
2. Add `index.html` to the root of the repo and push:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Add sorting algorithm visualizer"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. On GitHub, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Under **Branch**, select `main` and folder `/ (root)`, then **Save**.
6. Wait a minute, then visit `https://<your-username>.github.io/<your-repo>/`.

## Customize

- **Add an algorithm**: write a generator function that `yield`s `{type, idx, line}` steps (see the existing ones in the `<script>` block for the pattern), add it to the `GENERATORS` map, add a label to `LABELS`, pseudocode lines to `PSEUDOCODE`, and a row to `COMPLEXITY`.
- **Colors/fonts**: all design tokens are CSS custom properties at the top of the `<style>` block (`--bg`, `--accent`, `--mono`, etc.).
