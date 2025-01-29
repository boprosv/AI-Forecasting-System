# AI-Forecasting-System
Multi-Agent Workflow
Imagine you have a smart AI assistant that helps you analyze sales trends, predict future demand, and provide interactive insights. This assistant isn’t just a single AI—it’s a multi-agent system where different AI components work together, just like a well-organized team.

How This AI Forecasting System Works
The system follows a structured multi-agent workflow, where different AI components handle different tasks:

Understanding the User’s Request

When a user asks a question like "Forecast bike sales for the next 24 months," the Chat AI Agent first interprets the request.
It determines that the user needs:
Historical data (e.g., sales trends).
A future forecast (e.g., using machine learning).
A visualization (to present results clearly).
Retrieving Data with the SQL Agent

Once the request is understood, the SQL Agent:

Connects to the selected database (Walmart Sales or Bike Shop).
Generates an optimized SQL query to extract the required data.
Runs the query and retrieves relevant historical sales.

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-01-29%20110314.png?raw=true)

Making Forecasts with XGBoost

After retrieving data, the Forecasting Agent steps in. Instead of traditional statistical models (like ARIMA or Prophet), this system uses XGBoost Regressor—a powerful machine learning model for time-series forecasting.

XGBoost works by:

Training on past sales data to identify patterns.
Learning from features like seasonality, trends, and external factors.
Predicting future sales based on learned relationships.
This method is highly effective because:

It handles large datasets efficiently.
It adjusts to complex patterns better than traditional forecasting models.
It can incorporate additional features (e.g., holidays, promotions, weather, etc.).

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-01-29%20110526.png?raw=true)

Generating Insights & Visualizations

The Visualization Agent takes the XGBoost forecast and presents the results in an easy-to-understand way:
Interactive plots using Plotly.
Downloadable reports for further analysis.
Summarized insights so users quickly grasp the key trends.

How the Multi-Agent System Works Together
Think of this AI system as a team of specialized virtual assistants working together:

Chat AI (User Interface Agent) → Understands your question.
SQL Agent → Retrieves the necessary historical data.
XGBoost Forecasting Agent → Uses machine learning to make predictions.
Visualization Agent → Presents results clearly with interactive charts.
Each agent plays a role, passing data from one stage to the next, ensuring a smooth and accurate forecasting experience.

Example Scenario
Imagine you ask:
"Group the products by bike.description road vs mountain and call this group id. Aggregate the sales by month in each group in id. Forecast the next 24 months for each group by id. When plotting, make sure to use the id as the unique id."
