# Foundation Agent (Stage 0)

A minimal LLM-powered chatbot using Groq’s ChatCompletions API and Streamlit.
This agent is intentionally simple: no memory, no grounding, no frameworks.
It demonstrates how a raw LLM behaves before adding enterprise capabilities in later stages.

---

## Repository Structure

foundation_agent.py
requirements.txt
Procfile
.python-version
README.md

---

## Run Locally

1. Install dependencies:

2. Set your API key:
export GROQ_API_KEY="your_key_here"

3. Run the app:
streamlit run foundation_agent.py

---

## Deploying the App

You can deploy this same repository to either **Streamlit Cloud** or **Heroku**.

---

## Deploy to Streamlit Cloud (recommended for simplicity)

Streamlit Cloud automatically detects Streamlit apps and requires no Procfile.

**Steps:**
1. Push this repo to GitHub.
2. Go to https://share.streamlit.io
3. Connect your GitHub repository.
4. Select `foundation_agent.py` as the entry point.
5. Add an environment variable:

| Name         | Value        |
|--------------|--------------|
| GROQ_API_KEY | your_key     |

6. Deploy.

No setup.sh or runtime configuration is required.

---

## Deploy to Heroku

Heroku uses the included Procfile and `.python-version`.

### One-click deployment:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

### Manual deployment:

1. Login:
heroku login

2. Create an app:
heroku create my-foundation-agent

3. Set environment variable:
heroku config:set GROQ_API_KEY="your_key_here"

4. Deploy:
git push heroku main

5. Open the app:
heroku open

---

## Procfile (already included)


web: streamlit run foundation_agent.py --server.port=$PORT --server.address=0.0.0.0

---

## .python-version (already included)

3.11

Heroku will automatically select the latest patch version (e.g., 3.11.14).

---

## requirements.txt (already included)

streamlit
groq
python-dotenv

---

## Purpose of Stage 0

This agent represents the “raw LLM” stage:

- No conversational memory  
- No grounding or retrieval  
- No actions  
- No enterprise frameworks  
- No LangChain  

This stage helps users understand the limitations of a simple LLM before introducing more advanced features in later stages:
Stage 1 (Enterprise Framework), Stage 2 (Grounding), Stage 3 (Action Agents), and Stage 4 (Orchestration).

---
