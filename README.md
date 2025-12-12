## NYC Housing Violation and Complaints Analysis

Authors: Shreya Shetty (svs2148) and Shruti Shetty (ss7592)

This project analyzes housing maintenance code violations from HPD and housing-related 311 service requests for Manhattan between 2022–2025 to understand where, when, and how serious housing problems are for tenants. The code, data-processing steps, and results are organized as a Quarto website and rendered to the docs/ folder for deployment via GitHub Pages.

## Repository Structure
- [ ] `index.qmd`: Project introduction, motivation, research questions, brief overview of the two NYC Open Data sources, and a short nontechnical description of why comparing 311 complaints to Housing violations matters for renters and policy.

- [ ] `data.qmd`: Data description and cleaning. Explains the original HPD violation table and 311 service request table, Manhattan-only filtering, date parsing with mixed formats, manual mapping of descriptive text into unified categories (e.g., HEAT/HOT WATER, PLUMBING, PEST/SANITATION), and basic missingness patterns. Includes summary tables of key variables and missing values, plus justification for dropping or recoding some fields.

- [ ] `project_code_final.qmd`: Main analysis and results. Contains all category-comparison plots, quarterly and monthly time‑series graphs, the 2024 violation flow alluvial, building-level parallel coordinates, spatial samples, and severity/rent‑impairing summaries, with text explaining each figure. This file is the core of the analytical workflow.

- [ ] `conclusion.qmd`: High-level interpretation of the findings, limitations (e.g., potential batch‑loading artifacts, partial coverage for late 2025, unobserved informal complaints), and ideas for future work such as richer spatial models or linking to building registration data.

- [ ] `docs/`: Rendered HTML for all .qmd files plus site assets are saved here. This folder is the Quarto output directory configured in _quarto.yml for GitHub Pages deployment.

- [ ] `_quarto.yml`: Site configuration. Defines the project as a website, lists the pages (index.qmd, data.qmd, project_code_final.qmd, conclusion.qmd), sets the output directory to docs/, and controls shared options such as default figure sizes and theme.

> To view the whole project deployed on Github, please visit [shreyashetty2.github.io/edav_project/](https://shreyashetty2.github.io/edav_project/)

> You will need to download the raw CSV datasets from the NYC Open HPD website whose links are provided in data decription, and save it in `datasets/` folder to run the project locally.


## Render the book (RStudio)

- [ ] 1. If you haven't already, click "Help" "Check for Updates" to make sure you have the latest version of RStudio (and thus have Quarto installed.)

- [ ] 2. Render the web site locally by clicking the "Build" tap on the right and then "Render Book".

- [ ] 3. Use `browseURL("docs/index.html")` to view your book locally (or just open `docs/index.html` in a browser).

- [ ] 4. If it looks good, commit and push all changed files to GitHub. 

(You will need to repeat steps 2 and 4 every time you wish to update the book on GitHub Pages.)


## Reproducibility

- [ ] This project is built such that another person can rerun everything and recreate the website from scratch.

- [ ] All analysis lives in Quarto files: index.qmd (intro), data.qmd (data + cleaning), project_code_final.qmd (results), and conclusion.qmd (wrap‑up). Rendering once writes all HTML to docs/ using the site settings in _quarto.yml.

- [ ] Raw HPD and 311 CSVs should be stored in datasets/. Due to size limitations, the dataset could not be uploaded to Github but steps to retrieve data are mentioned in Data Decryption. Cleaning and transformations (date parsing, Manhattan filter, category mapping, derived variables) are done in code chunks, then saved as cleaned CSV/RDS files so others can either start from raw or from the cleaned versions.

- [ ] The repository is tracked with git/GitHub; all team members work on the same repo using branches and commits that describe major changes.

- [ ] Any steps that cannot run directly inside the Quarto files (such as downloading the NYC Open Data CSVs) are described in comments and text, with file names and links, so they can be repeated.

- [ ] Throughout the code, comments explain important choices (e.g., why time series were aggregated to months/quarters, why some plots use samples, why outlier spikes are treated as artifacts), making the reasoning and workflow clear for anyone who wants to reproduce or extend the analysis.
