# Adding a Notebook to the Book

This guide shows how to add a new tutorial to the BC Wildfire Predictive Service
Tutorials Book. It should take about two minutes.

## 1. Put the notebook in a lab folder

Drop your `.ipynb` file into one of the existing lab folders:

- `Intro_Wildfire_Mapping_Lab/`
- `Bayesian_Wildfire_Stats_Lab/`

Both folders are already linked into the `book/` build, so no extra wiring is needed.
Keep the filename descriptive — it stays exactly as you name it (we do **not** rename
notebooks to a `Chapter_XX` style).

If you want to start a brand-new lab folder, also add a symlink for it inside `book/`:

```bash
cd book
ln -s ../My_New_Lab My_New_Lab
```

## 2. Add a two-line entry to `book/_toc.yml`

Open `book/_toc.yml` and add an entry under `chapters:`, in the order you want it to
appear:

```yaml
  - file: Bayesian_Wildfire_Stats_Lab/My_New_Notebook
    title: "My New Notebook"
```

Note there is **no `.ipynb` extension** in the `file:` value — just the path without it.

### If your filename contains square brackets

Square brackets are parsed as glob patterns, so quote the whole `file:` value with
double quotes:

```yaml
  - file: "Bayesian_Wildfire_Stats_Lab/[Part_3]My_New_Notebook"
    title: "Part 3 - My New Notebook"
```

## 3. Add an "Open in Colab" badge

Add this as the **first markdown cell** of the notebook. Replace the path with your
notebook's path relative to the repository root:

```html
<a href="https://colab.research.google.com/github/vanislekahuna/wps-labs/blob/main/Bayesian_Wildfire_Stats_Lab/My_New_Notebook.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
```

### If your filename contains square brackets

URL-encode the brackets — `[` becomes `%5B` and `]` becomes `%5D`. For example,
`[Part_1]Rethinking_Predictors...ipynb` becomes:

```html
<a href="https://colab.research.google.com/github/vanislekahuna/wps-labs/blob/main/Bayesian_Wildfire_Stats_Lab/%5BPart_1%5DRethinking_Predictors_Why_Causal_Reasoning_Matters_in_Data_Science.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
```

Spaces should also be encoded as `%20`.

## 4. Preview the book locally

From the repository root:

```bash
pip install "jupyter-book<2.0"
jupyter-book build book
```

Then open `book/_build/html/index.html` in your browser. The build uses each notebook's
**saved outputs** (`execute_notebooks: off`), so you don't need Earth Engine or any
credentials to build the book. If your notebook's outputs are stale, re-run it in
Jupyter or Colab first and save it before committing.

To do a clean rebuild, delete `book/_build/` and run the build again.

## 5. How deployment works

Pushing to the `main` branch triggers the
[`deploy-book.yml`](../.github/workflows/deploy-book.yml) GitHub Actions workflow. It:

1. installs `jupyter-book<2.0` and the packages in `requirements.txt`,
2. runs `jupyter-book build book`,
3. uploads `book/_build/html` and deploys it to **GitHub Pages**.

So once your notebook and its `_toc.yml` entry are merged to `main`, the book rebuilds
and republishes automatically — no manual deploy step. You can also run the workflow by
hand from the **Actions** tab using **Run workflow**.

That's it. Add the notebook, add two lines to the TOC, push, and it's live. 🎉
