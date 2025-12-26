# Passpaper.com

---

# 📚 AI-Powered Learning Platform Backend 

## 📌 Overview

This repository contains the **Flask backend** for an AI-powered learning and assessment platform. The system supports **course delivery, quizzes, coding practice, automated evaluation, and AI-assisted learning features** such as lecture summarization, question generation, pseudocode generation, and code analysis.

The backend integrates **LLM APIs (Groq – LLaMA 3)** with a **relational database** to provide interactive, intelligent learning workflows.

---

## 🚀 Key Features

### 🎓 Course & Content Management

* Fetch available **courses, weeks, lectures, and quizzes**
* Structured delivery of **lectures, MCQs, and programming questions**
* Support for **video-based learning workflows**

### 🔐 Authentication & User Management

* User **signup, login, and logout** using `Flask-Login`
* Secure password hashing with **bcrypt**
* Session-based authentication

### 🧠 AI-Powered Learning Assistance

* **Lecture summarization** from DOCX files (complete & time-based partial summaries)
* **PDF summarization** with additional curated external learning links
* **Automatic MCQ generation** from lecture content
* **Pseudocode generation** for problem statements
* **Code analysis** for:

  * Bugs
  * Code smells
  * Security issues
  * Technical debt
* **Code feedback and improvement suggestions** using LLMs
* Interactive **AI chat endpoint**

### 🧪 Coding Practice & Evaluation

* Execute user-submitted Python code safely
* Run **public and private test cases**
* Provide detailed test results and feedback
* Separate **test-run** and **final submission** workflows

### 📊 Quiz Evaluation & Feedback

* Evaluate MCQ answers
* Generate **AI-based explanations and improvement suggestions**
* Provide **hints** without revealing answers

---

## ⚙️ Tech Stack

### Backend

* **Python**
* **Flask**
* **Flask-Login**
* **Flask-CORS**
* **SQLAlchemy**
* **bcrypt**

### AI & NLP

* **Groq API (LLaMA-3-8B)**
* Prompt-based LLM workflows for summarization, analysis, and generation

### File Processing

* **python-docx** (DOCX parsing)
* **PyPDF2** (PDF parsing)

### Database

* Relational database using **SQLAlchemy ORM**
* Models include: `User`, `Course`, `Week`, `Lecture`, `Question`, `Option`

---

## 🧱 Project Structure (Backend)

```text
app.py                # Main Flask application
models.py             # Database models
__init__.py            # App factory & extensions
src/assets/            # DOCX lecture files
public/                # PDF files
```

---

## 🔌 API Capabilities (High-Level)

| Feature             | Endpoint                                |
| ------------------- | --------------------------------------- |
| User Signup / Login | `/signup`, `/login`                     |
| Course Listing      | `/courses`, `/course/<id>`              |
| Lecture Summary     | `/content_summary`, `/pdf_summary`      |
| Question Generation | `/generate_questions`                   |
| Code Execution      | `/ppa_test_run`, `/ppa_submit`          |
| Code Analysis       | `/analyze`, `/feedback`, `/improvement` |
| Quiz Evaluation     | `/gaanswers`, `/paanswers`              |
| AI Chat             | `/chat`                                 |

---

## 🧠 AI Workflow Example

1. User selects a lecture
2. Backend extracts lecture text from DOCX/PDF
3. LLM generates:

   * Summaries
   * Questions
   * Feedback
   * Code analysis
4. Results returned as structured JSON

---

## 🛡️ Security & Reliability

* Password hashing with bcrypt
* Safe execution namespace for user code
* Input validation and structured error handling
* Separation of public/private test cases

---

### Run Instructions for Separate Servers

1.  **ENVIRONMENT (Flask)**:

    -   Open a terminal and navigate to your project directory:


        `cd project_path`

    -   CREATE Environment:


        `python -m venv .env`

    -   ACTIVATE Environment:


        `.\.env\Scripts\activate`


2.  **Backend (Flask)**:

    -   Open a terminal and navigate to your project directory:


        `cd project_path`

    -   Install the requirements.txt file:


        `pip install -r requirements.txt`

    -   Run your Flask server:


        `python app.py`

3.  **Frontend (Vue.js)**:

    -   Open another terminal and navigate to your project directory:



        `cd project_path`

    -   Install `NodeJS` If not Preinstalled on your System :

    -   Install dependencies (if not already done):


        `npm install`

    -   Run your Vue.js development server:

        `npm run serve`


3.  **Access Your Application**:

    -   Open your web browser and go to `http://localhost:8080` for the frontend.
    -   The Flask API will be running on `http://127.0.0.1:5000`.
