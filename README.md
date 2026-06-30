# CPstable – Changepoint Detection (R Shiny App)

An interactive **R Shiny application** for detecting and visualizing changepoints in time series data.

🔗 https://wiebkedammanntu.github.io/CPstable/

---

## 🧭 Overview

This application enables users to explore **structural changes in time series data**.  
Changes in experimental, technical, or environmental conditions may lead to shifts in the observed measurements. Detecting such **changepoints** helps identify stable time intervals where observations remain consistent and comparable.

The application is based on the methodology implemented in the R package `changepoint` (DOI: 10.32614/CRAN.package.changepoint) and provides an interactive interface for performing and visualizing changepoint analyses.

The app allows users to:

- 📤 Upload time series datasets *(or use a built-in example dataset)*  
- 📊 Visualize measurements over time  
- 🔍 **Detect changepoints** using the R package `changepoint`  
- ⚙️ Adjust detection sensitivity via a penalty parameter  
- 🧩 Explore changepoints across multiple variables  
- 📋 View detected changepoints and corresponding **segment means** in a table  
- 📄 Export results as a structured **HTML report**

---

## 📥 Input Data Format

The app expects an Excel file (`.xlsx`) with the following columns:

| Column | Description |
|------|-------------|
| `variable` | Name of variable being measured |
| `date` | Date (time point) of observation |
| `measurement` | Numeric measurement value |
| `group` | *(Optional)* grouping variable used to color-code observations in the plot |

➡️ An example dataset is included in the app and can also be downloaded.

---

## 📊 Changepoint Detection

Changepoints are estimated using methods from the **R package `changepoint`**.  
The application detects changes in the mean of a time series.

A **penalty parameter** controls the sensitivity of the changepoint detection:

- 🔽 Low values → more changepoints *(higher sensitivity)*  
- 🔼 High values → fewer changepoints *(lower sensitivity)*  
- ⚖️ Default value: `25 × log(n)` *(balaced, used for the example dataset)*  

A value of `2 × log(n)` corresponds to the standard **Bayesian Information Criterion (BIC)** penalty, which assumes independent observations.  
In many real‑world datasets, observations may exhibit dependencies or other structural relationships, which can make the BIC penalty overly sensitive. In such cases, larger penalty values may be more appropriate.

Users can interactively adjust the penalty value to explore how the number and location of detected changepoints change.

---

## 🔎 Visualization Features

- Slider to increase the plot size
- Variable ordering options:
  - Alphabetical order
  - Changepoint‑based order *(most recent changepoint at the top)*

---

## 🧪 Example Dataset

An example dataset is included for demonstration purposes and illustrates the changepoint detection functionality of **CPstable**.

The data originate from the **VICT3R database** (version 2.2.3, released on September 17, 2025; https://www.vict3r.eu/) and contain measurements from historical control animals used in toxicological studies.

**Dataset characteristics**

- Variables: 5 laboratory endpoints  
- Study type: 28‑day toxicity studies  
- Species: male Sprague‑Dawley rats  
- Source: multiple pharmaceutical companies *("groups" anonymized as A–J)*

The dataset can be downloaded directly from within the application.

---

## 👩‍💻 Authors

Developed by  
**Wiebke Dammann**  
**Kai Kammers**  
**Jörg Rahnenführer**

---

## 📬 Contact

For questions or feedback:

📧 wiebke.dammann@tu-dortmund.de
