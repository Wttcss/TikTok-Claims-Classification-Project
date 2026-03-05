<div align="center">

<img src="C:/Users/a/.gemini/antigravity/brain/104b5671-c8a7-4012-bd4e-50d72bf7bcf5/tiktok_claims_banner_1772685554386.png" alt="TikTok Claims Classification Project Banner" width="800" />
<br>

# TikTok Claims Classification Project

<!-- Badges -->
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](#)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](#)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-FF6F00?style=flat&logo=scikitlearn&logoColor=white)](#)

**Developing an automated moderation signal model to distinguish between claims and opinions.**

</div>

---

## 📖 Table of Contents
- [About the Project](#about-the-project)
  - [The Challenge](#the-challenge)
  - [Built With](#built-with)
- [PACE Strategy Overview](#pace-strategy-overview)
- [Key Insights & Findings](#key-insights--findings)
- [Next Steps & Recommendations](#next-steps--recommendations)
- [Getting Started](#getting-started)
- [License](#license)

---

## 🚀 About the Project

TikTok needs to automate the moderation of videos by distinguishing between **claims** (unverified information) and **opinions** (personal thoughts). Currently, the manual review process is backlogged. The goal of this project is to develop a machine learning model that streamlines the moderation process and provides a data-driven way to prioritize high-risk content for review.

### The Challenge
We analyzed **19,382 videos** to identify patterns that signal a "claim." The inspection phase focused on organizing the data, handling missing values (298 incomplete rows), and identifying key variables that drive continuous engagement and claim status.

### Built With

*   ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
*   ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
*   ![Jupyter](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)
*   ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

---

## 🧠 PACE Strategy Overview

This project was developed utilizing the **PACE** (Plan, Analyze, Construct, Execute) framework methodologies:

<div align="center">
<img src="C:/Users/a/.gemini/antigravity/brain/104b5671-c8a7-4012-bd4e-50d72bf7bcf5/pace_strategy_diagram_1772685639272.png" alt="PACE Strategy Framework Graphic" width="600" />
</div>

<br>

*   **Plan Stage:** Defined the distinct taxonomy for target variables ("Claim" vs. "Opinion"). Mapped variables to distinguish "signals" (e.g., view count) from "noise."
*   **Analyze Stage:** Identified that user engagement metrics (video likes and shares) are heavily right-skewed. Built summary dataframe statistics highlighting "Extreme Means" requiring robust non-parametric handling.
*   **Construct Stage:** *(Note: Adapted appropriately for specific machine learning classification requirements)*
*   **Execute Stage:** Investigated deep anomalies like Zero-Engagement Videos (high views but 0 likes/shares suggesting bot traffic) and verification bias.

---

## ✨ Key Insights & Findings

Based on the Exploratory Data Analysis (EDA) and data preprocessing phase:

<div align="center">
  <table>
    <tr>
      <td align="center"><strong>Metric</strong></td>
      <td align="center"><strong>Claims</strong></td>
      <td align="center"><strong>Opinions</strong></td>
    </tr>
    <tr>
      <td align="center">Dataset Split</td>
      <td align="center">50.3%</td>
      <td align="center">49.7%</td>
    </tr>
    <tr>
      <td align="center">Median Views</td>
      <td align="center">501,555</td>
      <td align="center">4,953</td>
    </tr>
  </table>
  <em>High views are a near-certain indicator of a claim.</em>
</div>

<br>

- 🚫 **Safety & Ban Correlation:** There is a significant correlation between account status and content type. Authors who are **banned or under review are 8x more likely** to have posted claims than opinions.
- 🔍 **Verification Gap:** The vast majority of claim-type content originates from unverified accounts.

---

## 🚀 Next Steps & Recommendations

1.  **Feature Engineering:** Further explore the `likes-to-view` and `share-to-view` ratios. These normalized metrics better distinguish claims from opinions than raw volume alone.
2.  **Modeling Strategy:** Prioritize non-parametric or tree-based models (e.g., Random Forest) to effectively handle the extreme outliers and statistical skew found in the engagement data.
3.  **Data Enhancements:** Incorporate Transcription/NLP (Speech-to-Text) data to predict outcomes directly from spoken content, and evaluate historical user behavior (`author_ban_status`).

---

## 🛠 Getting Started

To explore this project locally:

### Prerequisites
You need to have Python and Jupyter Notebook installed.

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/[your_username]/tiktok-claims-classification.git
   ```
2. Navigate to the project directory
   ```sh
   cd tiktok-claims-classification
   ```
3. Install required Python packages
   ```sh
   pip install pandas numpy scikit-learn
   ```
4. Open the Jupyter Notebook
   ```sh
   jupyter notebook
   ```

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.
