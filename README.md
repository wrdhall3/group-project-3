<div align="center">

# Earnings Call Analyzer  
### AI-Powered Insights for Earnings Transcripts  

<img src="images/Gradio_UI_Intro.png" alt="Earnings Call Analyzer UI" style="width:80%; height:auto;">

</div>

---

## Project Description
Insightful Consulting Group (ICG) is expanding into investment management and has been tasked with developing an AI prototype to streamline earnings report analysis. During earnings season, research analysts face an overwhelming influx of reports, making it difficult to extract valuable insights efficiently. This project enables users to query earnings call transcripts and receive instant, AI-driven responses to improve decision-making and efficiency.

## 📊 Dataset
The dataset consists of **earnings call transcripts from 2024**, retrieved dynamically from **API Ninja's financial transcript API** and formatted for **natural language processing (NLP)**. The dataset has been structured to allow for efficient retrieval of relevant financial insights. Each transcript contains:

- **Industry** - The sector in which the company operates.
- **Ticker Symbol** - The stock ticker used to identify the company.
- **Quarter** - The financial quarter in which the earnings call took place (Q1, Q2, Q3, Q4).
- **Year** - The fiscal year of the earnings call.
- **Transcript Text** - The full text of the earnings call, including statements from executives and analysts.
- **Date of Transcript** - The specific date when the earnings call occurred.

### 📁 Source
Earnings call transcripts are **retrieved in real-time** via **[API Ninja](https://api-ninjas.com/)**, which provides financial data, including company earnings reports. This allows the system to **fetch the latest transcripts dynamically**, ensuring up-to-date insights.

### 🔄 Data Preprocessing
To enhance retrieval accuracy and optimize response generation, several preprocessing steps are applied:

1. **API Data Extraction**
   - API requests are structured to fetch transcripts based on selected industry, company ticker, year, and quarter.
   - The API response is parsed and converted into a structured format.

2. **Text Cleaning & Standardization**
   - Special characters, excessive whitespace, and formatting inconsistencies are removed.
   - Speaker labels and interruptions are handled to improve readability.

3. **Tokenization & Chunking**
   - Transcripts are split into **manageable text blocks** to enhance search efficiency.
   - **Semantic chunking** ensures that responses are retrieved in context.

4. **Metadata Structuring**
   - Industry classifications and company tickers are normalized.
   - Date formats are standardized for consistency.

---

## 🛠️ Methodology
This project employs **retrieval-augmented generation (RAG)** in combination with **GPT-4 Turbo**, ensuring users receive **highly relevant and context-aware responses** when querying earnings call transcripts. The workflow consists of:

### 1️⃣ **Real-Time Transcript Retrieval**
   - The application **queries API Ninja** based on user-selected parameters.
   - If a transcript is available, it is **retrieved, processed, and stored temporarily** for querying.

### 2️⃣ **Query Matching & Context Extraction**
   - Users input financial-related questions.
   - The system **searches the retrieved transcripts** for relevant excerpts.
   - If an exact answer is found, it is **sourced directly from the transcript**.

### 3️⃣ **AI Enhancement via GPT-4 Turbo**
   - If no direct transcript match is found, **GPT-4 Turbo generates an AI-powered response**.
   - The AI model cross-references existing financial data for consistency.

### 4️⃣ **Evaluation & Response Scoring**
   - Every response is **scored for accuracy** using predefined metrics.
   - If an AI-generated response is used, a **confidence score** is assigned based on transcript alignment.

---

## 📏 Evaluation
The model is assessed based on **three primary evaluation metrics** to ensure reliability:

### ✅ **Faithfulness**
- Ensures that responses accurately reflect the earnings call transcripts.
- Minimizes hallucination risks in AI-generated content.

### 🎯 **Relevance**
- Measures how closely the response aligns with the **user’s query**.
- Prioritizes **direct transcript excerpts** over AI-generated answers.

### 🤖 **AI Confidence Score**
- AI responses are **ranked based on reliability**, factoring in:
  - **Transcript matching percentage**
  - **Financial data consistency**
  - **Linguistic and contextual accuracy**

Future updates will incorporate **user feedback loops** and **machine learning fine-tuning** to enhance response accuracy.
