🏗️ System Architecture
User → Streamlit → Text Extractor → Gemini Extraction API  
     → JSON Data → n8n Webhook → AI Analysis  
     → IF Condition → (Send Email or Skip) → Respond → Streamlit

📦 Folder Structure
AI-Document-Orchestrator/
│── app.py
│── requirements.txt
│── README.md
│── n8n_workflow.json
│── sample_docs/
│── assets/
│     └── architecture_diagram.png

⚙️ Setup Instructions
1️⃣ Clone Repository
git clone https://github.com/YOUR-USERNAME/AI-Document-Orchestrator
cd AI-Document-Orchestrator

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Configure Secrets

Create file:

.streamlit/secrets.toml


Add:

GEMINI_API_KEY = "your_api_key"
N8N_WEBHOOK_URL = "your_production_webhook_url"

4️⃣ Run the Streamlit App
streamlit run app.py

🔧 n8n Workflow Nodes

Your n8n workflow includes:

Webhook (POST) – receives JSON from Streamlit

AI Analysis Node – creates final answer

IF Node – checks business rule

AI Email Draft Node – creates email

Email Node – sends email (if TRUE)

Respond to Webhook – sends data back to Streamlit

Import the provided n8n_workflow.json into your n8n instance.

🚀 Deploying on Streamlit Cloud

Push repo to GitHub

Open https://share.streamlit.io

Select repository

Add secrets in project settings

Deploy
