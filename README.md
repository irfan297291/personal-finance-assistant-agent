# Personal Finance Assistant Agent

Gen AI Bootcamp — Session 5 | Module 5: LangChain Agents & Function Calling | AWS Bedrock

## What this is
An AI-powered personal finance assistant built with **LangChain Agents** and **AWS Bedrock**. The agent decides on its own which of 5 tools to call based on the user's message (function calling).

## Tools implemented
1. `calculate_expense` — logs an expense (amount, category, description) with today's date
2. `get_budget_status` — checks remaining budget for a category (food / transport / entertainment / shopping)
3. `convert_currency` — converts between currencies using hardcoded exchange rates
4. `calculate_savings_goal` — calculates months needed to reach a savings target
5. `get_spending_tip` — returns a money-saving tip for a spending category

## How to run
1. Install dependencies:
   ```bash
   pip install -q langchain langchain-aws langgraph boto3
   ```
2. Set your AWS Bedrock credentials as environment variables (do **not** hardcode them in the notebook):
   ```bash
   export AWS_ACCESS_KEY_ID=your_key
   export AWS_SECRET_ACCESS_KEY=your_secret
   export AWS_REGION=us-east-1
   ```
3. Open `personal_finance_assistant.ipynb` in Jupyter and run all cells top to bottom.

## Sample queries tested
| Query | Tools used |
|---|---|
| "I spent 50 USD on food today, convert it to PKR and log it" | convert_currency + calculate_expense |
| "What is my remaining budget for entertainment?" | get_budget_status |
| "I want to save 100,000 PKR. I can save 10,000 per month. When will I reach my goal?" | calculate_savings_goal |
| "I keep overspending on food, give me a money-saving tip" | get_spending_tip |
| "Log 2000 PKR for transport and show my transport budget status" | calculate_expense + get_budget_status |

Plus one custom compound query using `calculate_expense` + `get_spending_tip`.
