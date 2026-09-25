# 💰 Personal Finance Assistant Agent

<p align="center">
  <img src="https://img.shields.io/badge/LangChain-Agents-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-Bedrock-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/status-complete-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  <b>Gen AI Bootcamp — Session 5</b><br/>
  Module 5: LangChain Agents & Function Calling · AWS Bedrock
</p>

---

## ✨ What is this?

A friendly AI agent that manages your money the smart way — just talk to it in plain English (or Urdu-English 😄), and it figures out on its own which tool(s) to use. No menus, no buttons, just conversation → action.

Built with **LangChain Agents** + **AWS Bedrock (Amazon Nova 2 Lite)**, using real function calling — the agent reads your message, decides what needs to happen, calls the right tool(s), and replies like a helpful assistant.

> 🧠 Ask it to *"log 50 USD as food and convert it to PKR"* and it'll chain **two tools together** automatically. That's the magic of agentic AI.

---

## 🛠️ The 5 Tools

| # | Tool | What it does |
|---|------|---------------|
| 1 | 🧾 `calculate_expense` | Logs an expense with amount, category & description — timestamped automatically |
| 2 | 📊 `get_budget_status` | Checks how much budget is left in a category (food / transport / entertainment / shopping) |
| 3 | 💱 `convert_currency` | Converts between currencies (USD, PKR, EUR, GBP, AED) using fixed exchange rates |
| 4 | 🎯 `calculate_savings_goal` | Works out how many months it'll take to hit a savings target |
| 5 | 💡 `get_spending_tip` | Gives a practical money-saving tip for whichever category you're overspending in |

---

## 📊 Bonus: Live Visual Dashboard

Beyond the assignment requirements, this notebook renders a **polished dashboard** straight from the agent's own logged data:

- 📈 **Budget vs. Spend** bar chart — bars turn red the moment you go over budget
- 🍩 **Expense breakdown donut chart** — see where your money actually went
- 💹 **Savings goal progress chart** — visualize your path to the target

All auto-generated in Step 8 of the notebook — no extra setup needed.

---

## 🚀 How to run

1. **Install dependencies**
   ```bash
   pip install -q -U langchain langchain-aws langgraph boto3 botocore matplotlib pandas
   ```

2. **Set your AWS Bedrock API key** (never hardcode it — use an env var or `.env` file, and keep it out of Git!)
   ```python
   os.environ["AWS_BEARER_TOKEN_BEDROCK"] = "your-bedrock-api-key"
   os.environ["AWS_REGION"] = "ap-southeast-2"
   ```

3. **Open `personal_finance_assistant.ipynb`** and run all cells top to bottom 🎬

---

## 🧪 Sample queries tested

| Query | Tools chained |
|---|---|
| 💬 "I spent 50 USD on food today, convert it to PKR and log it" | `convert_currency` → `calculate_expense` |
| 💬 "What is my remaining budget for entertainment?" | `get_budget_status` |
| 💬 "I want to save 100,000 PKR. I can save 10,000 per month. When will I reach my goal?" | `calculate_savings_goal` |
| 💬 "I keep overspending on food, give me a money-saving tip" | `get_spending_tip` |
| 💬 "Log 2000 PKR for transport and show my transport budget status" | `calculate_expense` → `get_budget_status` |

Plus **one custom compound query** ✍️ combining `calculate_expense` + `get_spending_tip`.

---

## 🧰 Tech Stack

`Python` · `LangChain` · `LangGraph` · `AWS Bedrock` · `Amazon Nova 2 Lite` · `boto3` · `matplotlib` · `pandas`

---

<p align="center"><i>Built with ☕ and a lot of debugging AWS credentials 😅</i></p>
