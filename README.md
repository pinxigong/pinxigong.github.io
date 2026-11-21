# Pinxi Gong — Academic Homepage (Revised)

This is the **revised** static GitHub Pages website. All user-requested changes have been made to the main navigation, academic profile text, research headings, and research pages. No GitHub profile link, News section, Selected Coursework, or Contact section is included.

## Files

- `index.html` — homepage, with Publications & Presentations immediately after the introduction.
- `research/cp-als.html` — convergence analysis and experiment figures. Links to arXiv:2505.23046 as the inspiration for this research.
- `research/robust-pca.html` — proof strategy, theorem-based geometry schematic, benchmarking from the preprint, and original Figure 2 heatmaps (those two heatmap images are displayed directly from the official arXiv HTML page and therefore require an internet connection).
- `figures/rpca_benchmark.png`, `.svg` — two-panel graphic recreated from **Table 1** of arXiv:2601.21333v1.
- `figures/rpca_critical_point_geometry.png`, `.svg` — conceptual/illustrative geometry, **not** actual computed robust PCA objectives.
- `rpca_benchmark_data.csv` — numerical inputs transcribed from the paper's Table 1.
- `figures/01_*` to `05_*` — the five CP-ALS figures from the prior version.
- `cv.pdf` — your previously uploaded CV.
- `styles.css` — shared layout and responsive CSS.

## Publish updates

1. Back up any independent edits made to the live site.
2. Unzip the package and upload its **contents** (not the surrounding folder) into the root of `pinxigong/pinxigong.github.io`.
3. Overwrite existing `index.html`, `styles.css`, `cv.pdf` and files under `research/` and `figures/` when prompted. Commit changes to the `main` branch.
4. Confirm the site at `https://pinxigong.github.io/`. GitHub Pages will redeploy automatically.

The two arXiv-hosted heatmaps remain external for fidelity to the original publication and may require access to arxiv.org. Other included images are local.

## Scientific attribution and interpretation

The robust PCA runtime/recovery scatter graphic uses the 5 methods and reported averages in Table 1 of [Gong, Lai & Ma, arXiv:2601.21333v1](https://arxiv.org/abs/2601.21333), 10 synthetic instances, 10,000 × 8,000 matrices, search rank 400, true rank 200. This is not a new experiment. The two geometry panels are schematic toy cross-sections, not measured loss surfaces; exact-rank/overparameterized geometry results follow the paper's Theorem 1 and assumptions.

The CP-ALS numerical evidence remains from the provided experiment reports. The wording states the convergence proof as an ongoing goal, **not** as an already established result.
