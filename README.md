# Operation Phantom Ledger: Deloitte-Style Forensic Analytics Case Study

## 🏢 Executive Summary & Business Case
This project simulates a high-stakes corporate investigation at a major South African financial institution. Following a whistleblower alert regarding procurement non-compliance, this investigation utilizes advanced data engineering, statistical profiling, and financial intelligence to uncover a systematic employee-vendor collusion scheme. 

By cross-examining transactional logs against company registration data, the data pipeline isolates internal control bypasses and manual ledger manipulations designed to evade multi-executive oversight thresholds.

## 🛠️ Tech Stack & Architecture
* **Data Engineering & Exploration:** Python / `pandas` / `NumPy` / Jupyter Notebooks
* **Semantic Data Modeling:** Power BI Desktop / Star Schema Architecture
* **Calculation Engine:** Advanced Data Analysis Expressions (DAX)

---

## 🔍 Forensic Investigation Methodology & Findings

### Phase 1: Entity Collusion & Asset Sharing (Python)
Using conditional masks in `pandas`, the initial pipeline audited the vendor master file to detect duplicate banking assets hidden behind distinct Corporate Names and Registration structures.
* **The Discovery:** The system flagged multiple suppliers routing capital into the exact same South African bank account numbers (`12345678` and `87654321`), a definitive indicator of phantom vendors and shell company splits.

### Phase 2: Velocity & Threshold Evasion (Python + DAX)
The institution enforces a strict multi-executive approval requirement for any individual transaction exceeding a **R500,000 corporate governance ceiling**. 
* **The Discovery:** The script engineered a rolling chronological time-window delta grouping by `Approver` and `Vendor_ID`. The engine caught **Manager_A** processing two separate invoices for **Company_3** within a 45-minute window (`INV_FRAUD_A` for R420,000 and `INV_FRAUD_B` for R415,000). 
* **Interpretation:** By splitting a single massive expense into sequential lower values, the actor successfully kept each transaction beneath the tracking radar while moving a combined **R835,000** without authorization.

### Phase 3: Mathematical Ledger Profiling (Benford's Law)
To prove widespread structural data manipulation, the leading non-zero digits of every transaction amount were extracted and profiled against the expected logarithmic distribution of Benford's Law:
\[P(d) = \log_{10}\left(1 + \frac{1}{d}\right)\]

* **The Discovery:** The ledger exhibited a massive, statistically impossible variance from a natural distribution:
  * **Digit 1 Actual Frequency:** 57.69% (Expected: 30.10% | **+27.59% Variance**)
  * **Digit 3 Actual Frequency:** 28.85% (Expected: 12.49% | **+16.36% Variance**)
* **Interpretation:** This severe spike mathematically confirms manual data fabrication and systematic falsification of financial numbers to mask transactional patterns.

---

## 📊 Dashboard Architecture & DAX Metrics
The project was deployed onto a dark-themed executive canvas designed to prioritize focus onto outlier indicators:

1. **Total Transaction Volume ZAR:** Tracks cumulative procurement capital (R938,000.00).
2. **High Risk Threshold Value ZAR:** Isolates capital trapped inside policy breaches (R835,000.00).
3. **Benford's Law Combo Chart:** Provides visual mathematical confirmation of ledger tampering.
4. **Approver Risk Matrix:** Cross-tabs internal operational managers against supplier lines to uncover rogue approval paths.

### Core DAX Implementations:
```dax
Total Transaction Volume ZAR = SUM(final_forensic_ledger[Amount_ZAR])

High Risk Threshold Value ZAR = 
CALCULATE(
    [Total Transaction Volume ZAR],
    FILTER(
        final_forensic_ledger,
        final_forensic_ledger[Amount_ZAR] >= 400000
    )
)
```

## 🚀 Key Learning Outcomes & Professional Value
* Implemented real-world GRC (Governance, Risk, and Compliance) analytical mechanics.
* Demonstrated rigorous quantitative proofing techniques using statistical models.
* Designed an executive-level workflow bridging raw data pipelines directly into an intuitive, high-impact UI/UX.