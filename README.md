# ThatOperaNerd.github.io
Personal Website for MDS.

## Reproducibility Instructions

To clone this repository and completely rebuild the website locally, execute the following commands in order from your system terminal.

### Prerequisites
Ensure you have the following core software installed on your machine:
*   [Quarto CLI](https://quarto.org)
*   [R (v4.0 or higher)](https://r-project.org)
*   [uv (Python package manager)](https://astral.sh)

### Execution Steps

#### 1. Clone the Repository
```bash
git clone https://github.com/ThatOperaNerd/ThatOperaNerd.github.io.git
cd ThatOperaNerd.github.io
```

#### 2. Restore the Python Environment (`uv`)
Initialize the virtual environment capsule and install all pinned data processing and plotting libraries (`pandas`, `matplotlib`) using the project lockfile:
```bash
uv sync
```

#### 3. Restore the R Environment (`renv`)
Bootstrap the local R library container to download the isolated rendering and graphing packages (`knitr`, `rmarkdown`, `readr`, `dplyr`, `collapsibleTree`) exactly as specified in the project lockfile.

First, boot into your system's R console from the repository root:
```bash
R
```
Inside the R terminal interface, run the restoration command:
```R
renv::restore()
```
*(When prompted to confirm the installation of package dependencies, type `Y` and press Enter).*


#### 4. Compile and Render the Website
```bash
uv run quarto render
```