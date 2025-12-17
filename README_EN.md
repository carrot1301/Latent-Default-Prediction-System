# Adaptive Credit Scoring: Detecting Latent Risk in Consumer Lending

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
This project addresses a critical limitation in traditional unsecured lending: the inability to detect **"Loan Stacking"** behavior. Borrowers who continuously take new loans to pay off old ones often maintain a perfect repayment history until the moment of collapse.

We simulate a lending environment to contrast two modeling approaches:
1.  **Model A (Traditional):** Relies on historical repayment behavior (Reactive).
2.  **Model B (Adaptive):** Relies on affordability metrics and cash flow sustainability (Proactive).

## ⚠️ Problem Statement
Traditional credit scores often misclassify "Stackers" as low-risk borrowers because:
* Their repayment history is clean (paid by new debt).
* Default risk is deferred, not eliminated.

**Goal:** Build a model that flags unsustainable debt accumulation before default occurs.

## 🛠️ Tech Stack
* **Language:** Python
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn

## 📂 Methodology

### Phase 1: Data Simulation & Feature Engineering
* Generated a synthetic relational dataset (Customers, Loans, Transactions).
* Simulated "Hidden Risk" profiles: Borrowers with high income volatility and aggressive borrowing behavior.
* **Key Features Engineered:**
    * `DSR` (Debt Service Ratio)
    * `Residual Income`
    * `Debt Accumulation Rate`

### Phase 2: Modeling (Random Forest)
* **Model A:** Trained on demographics and past delinquency (blind to current leverage).
* **Model B:** Trained on financial health indicators (DSR, concurrent loans).
* **Result:** Model A failed to detect stackers (AUC ~0.5), while Model B achieved high accuracy (AUC > 0.9).

### Phase 3: Policy Simulation
* Simulated business outcomes for a portfolio of 2,000 customers.
* Compared **Strategy A** (Aggressive Growth) vs. **Strategy B** (Sustainable Lending).

## 📊 Key Findings
| Metric | Traditional Strategy | Adaptive Strategy |
| :--- | :--- | :--- |
| **Risk Detection** | Reactive (Misses hidden risk) | Proactive (Flags high DSR) |
| **Portfolio Growth** | High | Moderate (Rejects risky loans) |
| **Default Risk** | **Severe (Hidden losses)** | **Minimal (Sustainable)** |

> **Conclusion:** By sacrificing short-term loan volume from high-risk borrowers, the Adaptive Model prevents significant long-term losses, ensuring portfolio sustainability.

## 🚀 How to Run
1. Clone this repository.
2. Install dependencies: `pip install -r requirements.txt`
3. Run the notebooks in order:
    * `notebooks/1_Data_Generation.ipynb`
    * `notebooks/2_Modeling_Comparison.ipynb`
    * `notebooks/3_Policy_Simulation.ipynb`

## 📝 Author
* **Nguyen Tri Doan. Email: Doantri12343@gmail.com**
* *Note: This project uses synthetic data for educational and analytical demonstration purposes.*
