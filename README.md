# AI-Forecasting-System
Multi-Agent Workflow

The agent workflow in  AI Forecasting System is structured as a modular and dynamic pipeline, using LangGraph to orchestrate the logic between agents. Here's how it flows step-by-step:

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-06-13%20111203.png?raw=true)


![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-06-13%20114018.png?raw=true)

Agent Workflow Overview
The system is composed of four main agents:

SQL Agent

Forecast Agent

Chart Agent

Logic-Based Routing Agent

These agents collaborate to analyze user queries, extract data, forecast time series, and generate visualizations — all autonomously.

 Step 1: Routing Agent (Decision Maker)
Purpose: Decides which agents need to be activated.

Input: User’s natural language question.

Output:

json
Copy
Edit
{
  "sql_agent_required": "Yes",
  "forecast_agent_required": "No"
}
Logic:

If the user asks for data: SQL Agent only.

If the user asks for a prediction or trend: Both SQL + Forecast Agents.

🧾 Step 2: SQL Agent (Data Extraction)
Purpose: Understands and transforms user questions into SQL queries.

Workflow:

Preprocess user question for SQL relevance.

Generate SQL using LLM and table metadata.

Execute SQL on SQLite DB and return results as DataFrame.

Output:

SQL query string

Full DataFrame

Sample DataFrame (preview)

📈 Step 3: Forecast Agent (Time Series Prediction)
Purpose: Builds forecast models using the SQL data.

Workflow:

Preprocess the user question for forecasting intent.

Generate Python code that defines forecast_ts(data) using XGBoost or other ML models (XGBoost Regressor in our case).

Execute the code to generate a future prediction DataFrame.

Output:

Sample forecast

Full forecast (with confidence intervals)

📊 Step 4: Chart Agent (Visualization Generator)
Purpose: Produces interactive Plotly charts.

Workflow:

Generate Python chart code with plot_forecast(data).

Execute it dynamically.

Return a Plotly figure JSON to be rendered in Streamlit.

Output: Fully interactive Plotly chart with dropdowns for different time series.



![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-06-13%20114534.png?raw=true)
![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-06-13%20114336.png?raw=true)
![image alt]()
