# ai-data-analyst-agent
An AI-powered data analyst agent that enables users to analyse structured datasets using natural language. Upload one or more CSV files, ask business questions in plain English, and receive SQL queries, statistical analysis, and professional data visualisations without writing SQL or Python code.

The project combines **Google Gemini**, **DuckDB**, **Python**, **Pandas**, **Streamlit**, **Matplotlib**, and **R (ggplot2)** to build an intelligent multi-tool AI agent capable of autonomous data analysis.

---

## Project Overview

InsightForge was built to demonstrate how Agentic AI can automate business data analysis through intelligent tool orchestration rather than simple text generation.

Unlike traditional chatbots that respond from pretrained knowledge alone, the agent decides which analytical tools are required for each request, generates executable SQL or Python code, validates outputs, recovers from failures, and presents business-friendly insights grounded in real data.


### Key Features

- Natural language querying over structured datasets
- Automatic SQL generation with multi-table JOIN support
- Intelligent Python statistical analysis
- Automatic chart generation based on user intent
- Professional visualisations using R (ggplot2) with Matplotlib fallback
- Plain-English interpretation of analytical results
- Self-correcting SQL and code generation
- Secure sandboxed code execution
- Multi-file CSV upload with automatic relational table creation
- Conversation history management

---

## Problem Statement

Business users often need quick answers from their data, such as identifying top-performing products, analysing customer behaviour, or understanding revenue trends. Obtaining these insights traditionally requires writing SQL queries, creating Python scripts, or waiting for data analysts to perform the analysis.

Most conversational AI systems also struggle with analytical tasks because they generate responses directly from language models instead of executing real analytical workflows.

---

## Solution

InsightForge solves this challenge by combining large language models with specialised analytical tools.

The agent intelligently determines whether a user's request requires SQL querying, statistical analysis, data visualisation, or a combination of these tools. Each tool generates executable code that runs against real datasets, allowing the agent to produce accurate, explainable, and business-ready insights.

Instead of guessing answers, InsightForge reasons over actual analytical results before generating its final response.

---

## System Architecture

```text
                User Question
                      │
                      ▼
            Agent Orchestrator
          (Tool Routing Decision)
                      │
      ┌───────────────┼────────────────┐
      ▼               ▼                ▼
 SQL Generator   Python Analysis   Chart Generator
      │               │                │
      ▼               ▼                ▼
    DuckDB       Pandas Analysis   R / Matplotlib
      └───────────────┼────────────────┘
                      ▼
          Plain-English Interpreter
                      │
                      ▼
             Streamlit User Interface
```

---

## Technology Stack

| Layer | Technology |
|--------|------------|
| LLM | Google Gemini (gemini-3.5-flash-lite) |
| Database Engine | DuckDB |
| Data Processing | Pandas |
| Statistical Analysis | Python |
| Visualisation | Matplotlib |
| Advanced Visualisation | R + ggplot2 |
| User Interface | Streamlit |
| Programming Language | Python 3.12 |
| Code Execution | Python Subprocess Sandbox |

---

## 📂 Project Structure

```text
ai-data-analyst-agent/
│
├── app/
│   ├── data/
│   │   └── loader.py
│   │
│   ├── orchestrator/
│   │   ├── router.py
│   │   ├── nl_to_sql.py
│   │   ├── nl_to_code.py
│   │   ├── nl_to_chart.py
│   │   ├── nl_to_r_chart.py
│   │   ├── schema_utils.py
│   │   ├── gemini_utils.py
│   │   └── agent.py
│   │
│   ├── tools/
│   │   ├── sql_tool.py
│   │   ├── chart_tool.py
│   │   ├── r_chart_tool.py
│   │   └── interpreter.py
│   │
│   └── sandbox/
│       └── executor.py
│
├── frontend/
│   └── streamlit_app.py
│
├── data/
│   └── raw/
│
├── tests/
│
├── requirements.txt
├── .env.example
└── README.md
```

---

## 🔄 Agent Workflow

The complete analysis pipeline follows these stages:

1. Upload one or more CSV datasets.
2. Automatically create relational tables in DuckDB.
3. Analyse the database schema.
4. Route the user's request to the required analytical tools.
5. Generate executable SQL queries.
6. Execute SQL against DuckDB.
7. Perform Python statistical analysis when required.
8. Generate professional visualisations when requested.
9. Interpret analytical results using the language model.
10. Return a complete business-friendly response through the Streamlit interface.

---

## Agent Decision Process

Rather than executing every available tool, InsightForge first determines what the user's question actually requires.

Depending on the request, the agent may choose:

- SQL only
- SQL + Python analysis
- SQL + Chart generation
- SQL + Python + Chart generation

This routing strategy improves efficiency while reducing unnecessary computation and API usage.

---

## Preview

<!-- ![InsightForge demo](screenshots/demo-screenshot.png) -->



---

## Safety Features

InsightForge includes several engineering features designed to improve reliability and robustness.

- Sandboxed execution of generated Python and R code
- Automatic retry and self-correction after execution failures
- Fail-fast handling for API quota limits
- SQL execution grounded on the actual database schema
- Interpretation generated only from real analytical outputs
- Automatic fallback from R (ggplot2) to Matplotlib

---

## Installation

### Clone the repository

```bash
git clone https://github.com/Uzo-Hill/ai-data-analyst-agent.git

cd ai-data-analyst-agent
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Configure environment variables

Create a `.env` file.

```text
GEMINI_API_KEY=your_api_key_here
```

### Run the application

```bash
streamlit run frontend/streamlit_app.py
```

---

## 💻 Usage

1. Launch the Streamlit application.
2. Upload one or more related CSV datasets.
3. Ask analytical questions in plain English.
4. Review the generated SQL, statistical analysis, visualisations, and business insights.

---

## 📈 Example Questions

- What is the total revenue by category?
- Which city has the most customers?
- Show total revenue across all product categories.
- What is the correlation between discount percentage and quantity ordered?
- Visualise the top ten best-selling products by revenue.

---

## Future Improvements

- Auto-generated dashboard generation
- FastAPI backend
- Docker deployment
- Persistent database support
- Multi-chart reporting
- Enhanced analytical capabilities

---

## 👤 Author

**Hillary Uzoh**

**Data Scientist | AI Engineer**
























