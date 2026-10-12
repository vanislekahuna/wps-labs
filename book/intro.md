# BC Wildfire Predictive Service | Tutorials Book

[← Home Page](https://vanislekahuna.github.io)

Welcome to the **BC Wildfire Predictive Service (`wps`) Tutorials Book** — a growing
collection of hands-on lab tutorials that bridge the gap between advanced technology
and practical wildfire management.

> Our mission is to increase awareness, collaboration, and education on the applications
> of remote sensing and machine learning to wildfire research.
>
> By increasing exposure to the challenges of wildfires amongst the wider Data Science
> community, we strive to empower leaders with the tools to make optimal decisions which
> minimize the loss that communities and wildlife suffer.

Each tutorial is carefully crafted to build foundational knowledge while tackling
real-world challenges, such as early fire detection, perimeter mapping, and burn
severity assessment. Whether you're a data scientist looking to apply your skills to
environmental challenges, or a wildfire researcher seeking to leverage machine learning,
you'll find resources here to support your journey.

## 📚 What's Inside

This book collects the notebooks from the repository's two labs:

**Intro Wildfire Mapping Lab**

- **Mapping BC Wildfires with Google Earth Engine** — get started building wildfire
  perimeters with Earth Engine, `geemap`, and `folium`.

**Bayesian Wildfire Stats Lab**

- **Bayesian Simple Linear Regression with PyMC** — a first pass at Bayesian regression
  on wildfire data, and the limits of what a simple model can tell you.
- **Part 1 — Rethinking Predictors** — why causal reasoning matters before you reach for
  a regression.
- **Part 2 — Putting DAGs to the Test** — what regression reveals (and hides) about
  wildfire drivers.
- **Explaining Markov Chain Monte Carlo** — MCMC by way of wildfire forensics.
- **Reverse-Engineering Hamiltonian Monte Carlo** — the engine behind modern Bayesian
  inference, built up from scratch.

## 🚀 How to Use This Book

### Read online

Navigate the tutorials using the sidebar. Each tutorial renders with its saved outputs,
so you can read the narrative, code, and figures without running anything.

### Run it yourself in Colab

Every notebook carries an **Open in Colab** badge. Click it to open the notebook in
Google Colab and run the cells interactively. Note that some labs require credentials
(for example, an Earth Engine project via the `CYBERSE` environment variable) — see the
individual lab README for setup.

### Preview locally

```bash
pip install "jupyter-book<2.0"
jupyter-book build book
# then open book/_build/html/index.html
```

## ➕ Adding a Tutorial

Adding a new notebook is nearly zero-effort. Drop the notebook into one of the lab
folders, add a two-line entry to `book/_toc.yml`, and push to `main` — the GitHub Actions
workflow rebuilds and republishes the book automatically.

Full instructions, including the bracket-quoting and URL-encoding gotchas for
filenames with special characters, are in [ADDING_A_NOTEBOOK.md](ADDING_A_NOTEBOOK.md).

## 🙏 Acknowledgments

This book builds on the tutorials contributed by the BC Wildfire Predictive Service
community, and reuses the Jupyter Book scaffolding from the
[Statistical Rethinking with PyMC](https://github.com/vanislekahuna/Statistical-Rethinking-PyMC)
book.

---

<div style="text-align: center; margin-top: 40px; padding: 20px; background-color: #f5f5f5; border-radius: 8px;">
  <p style="font-size: 1.1em; margin: 0;">
    <strong>Questions or feedback?</strong> Open an issue on our
    <a href="https://github.com/vanislekahuna/wps-labs">GitHub repository</a>
  </p>
</div>
