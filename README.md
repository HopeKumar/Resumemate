# ResumeMate 🧠  
**AI-Assisted Resume Analyzer using Gemini LLMs**

ResumeMate is an AI-assisted resume analysis system that compares a candidate’s resume with a job description and generates **explainable, ATS-inspired feedback**.  
It is designed as a **decision-support tool**, simulating how recruiters and Applicant Tracking Systems (ATS) evaluate resumes — without fabricating experience or hiding logic.

---

## 🚀 Features

- 📄 Resume and job description analysis (plain text)
- 🎯 ATS-inspired skill matching (heuristic-based)
- 📊 Explainable match score (0–100)
- ✍️ Weak resume bullet detection and rewriting
- 📉 Skill gap identification (critical vs secondary)
- 🤖 ATS keyword improvement suggestions (no stuffing)
- 🧭 Career guidance recommendations
- 🛡️ Robust Gemini API integration with retries, fallbacks, and mock mode

---

## 🛠 Tech Stack

- **Language:** Python  
- **LLM:** Google Gemini (gemini-1.5-flash / gemini-2.5-flash)  
- **Runtime:** Kaggle Notebook / Jupyter  
- **Secrets Management:** Kaggle Secrets or environment variables  

---

## 🧠 How ResumeMate Works

1. The user provides:
   - Resume text
   - Job description text
2. The system sends both inputs to Gemini under **strict constraints**
3. Gemini performs structured analysis:
   - Skill extraction
   - Requirement classification
   - Match scoring with explanation
   - Resume bullet rewriting
4. ResumeMate parses the LLM output using **defensive JSON extraction**
5. A consolidated, structured report is generated

> ⚠️ ResumeMate focuses on **explainability and reliability**, not blind automation.

---

## ⚙️ How to Run

### Option 1: Run on Kaggle (Recommended)

1. Upload `resumemate_gemini.ipynb` to Kaggle
2. Add your Gemini API key:
   - Go to **Account → Secrets**
   - Name: `GEMINI_API_KEY`
3. Enable **Allow access to secrets** in notebook settings
4. Run all cells

---

### Option 2: Run Locally (Optional)

```bash
export GEMINI_API_KEY=your_api_key_here
```
Then open the notebook and run all cells.

## 📄 Example Output
```
{
  "match_score": 50,
  "missing_critical_skills": ["REST APIs"],
  "rewritten_bullets":
 [
    {
      "before": "Worked on Python scripts for automation.",
      "after": "Developed Python scripts to automate routine tasks."
    }
  ]
}
```
## 🔐 Security & Reliability

API keys are never hardcoded

Supports:

Environment variables

Kaggle Secrets

Includes:

Retry logic with exponential backoff

Mock mode if API key is missing

Hardened JSON parsing to handle LLM inconsistencies


## ⚠️ Limitations (Important)

ResumeMate does NOT:

Act as a real ATS system

Automatically apply to jobs

Scrape job boards

Fabricate experience or metrics

Replace human judgment

It is intended as a decision-support and learning tool, not a magic solution.


## 📌 Motivation

This project was built to explore:

Robust LLM system design

Prompt constraint engineering

Explainable AI outputs

Secure and production-aware API integration

Rather than focusing on flashy UI, ResumeMate prioritizes engineering correctness and transparency.

## 📜 License

This project is released for educational and portfolio use.

👤 Author

J Hope Kumar
📧 kumarhope2018@gmail.com

🔗 LinkedIn: https://linkedin.com/in/12HOPE
