
# Risk Insight Copilot: Financial Risk Analyzer

**Course:** SEP 769 – Cyber Physical Systems  
**Group Members:** Kushal Shah, Jenil Virani, Sarthak Paliwal  
**Term:** Summer'25 

## Project Overview

The ‘Financial Risk Copilot’ is an AI powered financial analyst that reviews 10-Ks and determines the risk level of any publicly listed company. This idea stems from the issue of individual investors and beginner analysts having a hard time analyzing millions of data points to accurately identify the risk associated with any investment.
 
## Repository Structure

```
financial-risk-analyzer/
│
├── env/                          # Environment configuration (environment.yml)
│
├── notebooks/                   # All project notebooks (step-by-step pipeline)
│   ├── STEP_1_10-K_Extraction.ipynb
│   ├── STEP_2_10-K_sort.ipynb
│   ├── STEP_3_Item1A_Item7_extraction.ipynb
│   ├── STEP_4_convert_to_parquet.ipynb
│   ├── STEP_5_LangChain_Integration.ipynb
│   ├── STEP_6_DL_data_cleaning.ipynb
│   ├── STEP_7_Feature_eng_text_embeddings.ipynb
│   ├── STEP_8_Parquets_division_batchWise.ipynb
│   └── STEP_9_Modelling.ipynb
│
├── .gitignore                   # Hidden files & API keys excluded from repo
└── README.md                    # This file
```

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/kushalshah1303/financial-risk-analyzer.git
cd financial-risk-analyzer
```

### 2. Create Conda Environment

Make sure you have Anaconda installed, then run:

```bash
conda env create -f env/environment.yml
conda activate financial-risk-analyzer
```

### 3. API Key Configuration

To run the LangChain+Groq integration, create a `.env` file with the following format:

```
GROQ_API_KEY=your_actual_api_key_here
```

> ⚠️ The `.env` file is excluded in `.gitignore` for privacy.

## Notes

- Due to token limits, only ~600 rows were processed in the LLM step (free Groq API cap).
- Data files (`.parquet`, `.csv`) and large model outputs are not uploaded due to size, but can be generated when the code is run step by step.
- All notebooks are clean, commented, and execute without error under the provided environment.


## 🧪 How to Run the Code

Execute the notebooks in the following sequence for full pipeline execution:

1. `STEP_1_10-K_Extraction.ipynb` – Download and extract 10-K filings  
2. `STEP_2_10-K_sort.ipynb` – Organize and filter filings  
3. `STEP_3_Item1A_Item7_extraction.ipynb` – Extract sections of interest  
4. `STEP_4_convert_to_parquet.ipynb` – Save structured data  
5. `STEP_5_LangChain_Integration.ipynb` – Extract risk narratives using LLM  
6. `STEP_6_DL_data_cleaning.ipynb` – Clean and structure LLM outputs  
7. `STEP_7_Feature_eng_text_embeddings.ipynb` – Generate FinBERT embeddings  
8. `STEP_8_Parquets_division_batchWise.ipynb` – Efficient memory handling  
9. `STEP_9_Modelling.ipynb` – Train and evaluate neural network model


## 🛠 Dependencies

- Python 3.10+
- LangChain
- Transformers (FinBERT)
- Torch
- Pandas, NumPy, Matplotlib, Seaborn
- BeautifulSoup, Regex, tqdm
- dotenv (for API handling)

See `env/environment.yml` for full dependency list.

## Contact

For any questions or setup issues, please reach out to us.
