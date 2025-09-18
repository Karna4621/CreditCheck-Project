

**Project Description**
This project implements a creditworthiness classification system for business partners using  Python, LangGraph , Groq LLMs for intelligent validation and monitoring, and Random Forest as the classifier. 
The workflow automates data preprocessing, quality validation, model inference, monitoring for drift, and retraining decisions, with human-in-the-loop AI agent oversight to ensure correctness and compliance.

***The working file is a jupyter notebook developed and executed in Kaggle (www.kaggle.com) . Recommend the same while testing 
If running locally Input file path changes are needed.***

## Crucial Steps and Agents
- **Data Preprocessing Agent:** Checks for required columns and consistency, cleans null or invalid values, handles outliers using IQR clipping, and normalizes numeric features.
- **Validation Agent:** Uses Groq LLM to generate a comprehensive data quality and readiness report, combined with human approval before modeling.
- **Inference Agent:** Runs a Random Forest classifier on preprocessed features, predicting creditworthiness with confidence scores.
- **Monitoring Agent:** Leverages the LLM to analyze prediction distributions and confidence metrics against historical baselines to detect drift and suggests retraining if needed.
- **Human-in-the-Loop AI Agent:** Summarizes monitoring insights for human reviewers and captures their retraining confirmation or rejection, finalizing the pipeline outcome.

## Dataset Variables in `credit_partners.csv`
The dataset contains 100 samples with these key variables capturing business and financial metrics for credit assessment:

- `Partner ID`: Unique identifier for each partner
- `Experience in yrs`: Years of business experience (numeric)
- `cibil score`: Credit score (numeric)
- `Monthly Sales`: Monthly sales revenue (numeric)
- `Any other profitable business`: Indicator/count of other businesses (numeric)
- `Inventory turnover ratio`: Inventory efficiency ratio (numeric)
- `Asset holdings in value`: Monetary asset holdings in USD (numeric)
## Assumptions
- Classifier model outputs are generated randomly with predcitions and probabilities
- All the data is hypothetical and for demo purpose only
- Prompts are generic and not intended for production use
- Historical baseline metrics exist for model drift analysis.
- Human reviewers confirm quality and retraining decisions based on AI agent summaries.
- Groq LLM supports prompts for validation, monitoring, and summarization tasks.

## Summary of Results at Decision Nodes using LLMs

**Validation Node**
The LLM produces detailed validation reports confirming data completeness, statistical distributions, and outlier evaluation. Human reviewers approve the dataset before proceeding.
**Monitoring Node**
Real-time prediction distribution and confidence scores are analyzed by the LLM against historical baselines. The LLM recommends retraining due to observed accuracy drops and confidence reduction. The recommendation is confirmed by human reviewers before model retraining is initiated.


