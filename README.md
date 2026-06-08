# Technical Challenge — Sourcing Analysis with AI

> Sourcing funnel analysis with applied AI for candidate prioritization support.

## Objective

Analyze a fictional sourcing/recruitment dataset to answer:

- Which sourcing strategies convert best?
- What signals indicate a higher chance of advancement?
- When is it worth persisting with a candidate?
- When is conversion probability too low to justify effort?
- Are there meaningful patterns by channel, recruiter, or candidate profile?

## Repository Structure

```
sourcing-analysis-challenge/
├── README.md
├── requirements.txt
├── notebooks/
│   └── 01_sourcing_analysis.ipynb
├── data/
│   └── mock_sourcing_dataset_clean.csv
└── docs/
    └── sourcing_challenge_final.md
```

## Key Insights

| Channel | Candidates | Hire Rate | Response Rate |
|---|---|---|---|
| GitHub | 73 | 11.0% | 68.5% |
| Inbound | 69 | 10.1% | 79.7% |
| Hunting | 75 | 9.3% | 64.0% |
| Talent Pool | 68 | 8.8% | 75.0% |
| LinkedIn | 81 | 8.6% | 63.0% |
| Community | 89 | 7.9% | 67.4% |
| Event | 82 | 4.9% | 67.1% |
| Referral | 64 | 4.7% | 59.4% |

### Overall Funnel

| Stage | Candidates | Cumulative Conversion |
|---|---|---|
| Sourced | 601 | 100% |
| Response | 408 | 67.9% |
| Screening | 308 | 51.2% |
| Interview 1 | 234 | 38.9% |
| Assessment | 201 | 33.4% |
| Offer | 62 | 10.3% |
| **Hired** | **49** | **8.2%** |

## AI Usage

A **Logistic Regression** model was built to estimate the probability of hire based on variables such as sourcing channel, seniority, location, work mode, and response time. The model achieved **AUC = 0.690** and is used as a pipeline prioritization tool — not as an automated decision-maker.

The AI workflow follows a **human-in-the-loop** approach:
1. The model generates a priority ranking based on estimated hire probability
2. The recruiter validates with qualitative context
3. The team reviews false positives/negatives monthly
4. The model is recalibrated with new data

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/juliacintral/sourcing-analysis-challenge.git
cd sourcing-analysis-challenge

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
jupyter notebook notebooks/01_sourcing_analysis.ipynb
```

## Recruiter Recommendations

- **Prioritize GitHub, Inbound, and Hunting** for profiles with the strongest final conversion
- **Set a first-contact SLA** — delays in outreach reduce funnel advancement
- **Use technical score + response time together**, not in isolation
- **Build prioritization queues**: high, medium, and low conversion probability
- **Reactivate the Talent Pool** for candidates with role alignment and fast response history
- **Distinguish operational failures** (closed headcount, timing) from sourcing quality failures

## Tech Stack

- Python 3.x
- pandas, numpy
- scikit-learn (Logistic Regression)
- Jupyter Notebook

## Final Report

The file `docs/sourcing_challenge_final.md` contains the full written report including:
- Approach and decisions made
- Detailed funnel analysis
- Channel-by-channel comparison
- Advancement signals and low-potential indicators
- AI usage in the workflow
- Practical recommendations

---
*Technical Challenge — People Analytics & Sourcing with AI*
