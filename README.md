# Food Rescue AI

Food Rescue AI is an AI-for-sustainability project aligned with **SDG 12: Responsible Consumption and Production**. It helps restaurants, hotels, campuses, and event organizers assess surplus food, retrieve safety guidance, identify donation partners, estimate environmental impact, and generate donation reports.

This repository contains two parts:

- `artifacts/food-rescue-ai/` — the polished React/Vite dashboard used for the interactive demo.
- `food_rescue_ai/` — the Python/Streamlit reference implementation with LangChain, FAISS, Sentence Transformers, an optional IBM Granite adapter, sample datasets, a local knowledge base, and submission documents.

## Demo features

- Command center with rescue metrics and active surplus
- Grounded food-donation safety assistant
- Surplus forecasting
- City-aware NGO and food-bank directory
- Environmental impact calculator
- CSV and PDF report generation
- RAG methodology and architecture
- Responsible AI checklist
- 12-slide presentation outline
- Five-minute demo script

## Run the React dashboard

Requirements: Node.js 20+ and pnpm.

```bash
pnpm install
PORT=5173 BASE_PATH=/ pnpm --filter @workspace/food-rescue-ai run build
PORT=5173 BASE_PATH=/ pnpm --filter @workspace/food-rescue-ai run dev
```

Open the local URL printed by Vite.

## Run the Python/Streamlit reference project

```bash
cd food_rescue_ai
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

The RAG implementation uses FAISS and Sentence Transformers when those dependencies and models are available. It falls back to a labelled keyword index so the prototype remains usable offline.

To connect an IBM Granite-compatible hosted endpoint, set the values from `food_rescue_ai/.env.example` in your runtime environment. Do not commit credentials.

## Project documentation

- `food_rescue_ai/architecture.md` — Mermaid and text architecture diagrams
- `food_rescue_ai/responsible_ai.md` — fairness, transparency, privacy, ethics, and bias mitigation
- `food_rescue_ai/presentation_outline.md` — complete 12-slide presentation content and speaker notes
- `food_rescue_ai/demo_script.md` — five-minute presentation walkthrough
- `food_rescue_ai/README.md` — Python project details

## Safety and data notice

The included datasets and knowledge-base documents are synthetic or educational placeholders for a prototype. Replace them with current local food-safety rules, validated environmental factors, and consented partner data before real-world use. The assistant is decision support and does not replace a trained food-safety lead or legal review.
