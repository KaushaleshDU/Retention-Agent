# Retention-Agent

Offline customer retention agent combining XGBoost churn prediction, FAISS retrieval-augmented generation (RAG), and LangChain.

## Overview

This project demonstrates an end-to-end customer retention workflow:
- Train and evaluate a churn prediction model using Telco customer data.
- Store product and FAQ content in FAISS semantic indexes for fast local retrieval.
- Combine churn prediction outputs with retrieved knowledge for customer retention guidance.

## Key Components

- `agent.ipynb` - Interactive agent demo and insight generation.
- `build_indexes.ipynb` - Notebook for creating FAISS indexes from product and FAQ content.
- `churn_model.ipynb` - Notebook for training, evaluating, and exporting the churn model.
- `data/` - Raw datasets used for modeling and retrieval.
- `models/` - Serialized model artifacts:
  - `churn_model.pkl`
  - `label_encoders.pkl`
  - `scaler.pkl`
- `indexes/` - Prebuilt FAISS indexes and chunk metadata for retrieval.

## Setup

1. Create and activate a Python virtual environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Configure environment variables if needed.
- Add provider API keys in a `.env` file if external services are required.
- Example keys may include `OPENAI_API_KEY` or `GOOGLE_API_KEY`.

> Do not commit `.env` or secret credentials to version control.

## Usage

Open the notebooks in Jupyter or VS Code and run the cells in order:
1. `churn_model.ipynb` - build and evaluate the churn predictor.
2. `build_indexes.ipynb` - generate FAISS indexes from the knowledge data.
3. `agent.ipynb` - explore the combined retention agent experience.

## Data Files

- `data/WA_Fn-UseC_-Telco-Customer-Churn.csv` - Telco churn dataset used for model training.
- `data/products.csv` - Product catalog content for retrieval.
- `data/fact-base-tesco.csv` - FAQ or knowledge base content used in the agent.

## Notes

- The project is designed for local experimentation with customer retention workflows.
- The FAISS indexes enable fast semantic search without requiring internet access for query retrieval.
- Update the notebooks and model files as needed to adapt to new data or retention scenarios.

