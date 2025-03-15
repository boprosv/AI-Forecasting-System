# Multi-Agent AI-Forecasting-System
Multi-Agent Workflow
Imagine you have a smart AI assistant that helps you analyze sales trends, predict future demand, and provide interactive insights. This assistant isn’t just a single AI—it’s a multi-agent system where different AI components work together, just like a well-organized team.

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20101345.png?raw=true)

How This AI Forecasting System Works:

The system follows a structured multi-agent workflow, where different AI components handle different tasks:

Understanding the User’s Request

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20164325.png?raw=true)

When a user asks a question like "Aggregate the sales data by multiplying the bike unit price × the quantity and sum by day. Forecast the transactions by day for the next 365 days.," the Chat AI Agent first interprets the request.
It determines that the user needs:
Historical data (e.g., sales trends).
A future forecast (e.g., using machine learning).
A visualization (to present results clearly).
Retrieving Data with the SQL Agent

Once the request is understood, the SQL Agent generates code:

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20164345.png?raw=true)

Connects to the selected database (Walmart Sales or Bike Shop).
Generates an optimized SQL query to extract the required data.
Runs the query and retrieves relevant historical sales.


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

Here is the glimps of a forecast code generated by Forecast Agent

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20165001.png?raw=true)

Generating Insights & Visualizations

The Visualization Agent takes the XGBoost forecast and presents the results in an easy-to-understand way:
Interactive plots using Plotly. Here is a glimps of code generated by Visualization Agent:

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20165636.png?raw=true)

And here is the fully interactive forecast chart:

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20171220.png?raw=true)

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-15%20171236.png?raw=true)

In the next window you get a predicted outcome:

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-13%20160049.png?raw=true)

You can inspect and download outcome:

![image alt](https://github.com/boprosv/AI-Forecasting-System/blob/main/Screenshot%202025-03-13%20160106.png?raw=true)

Why This Approach is Powerful
XGBoost is More Accurate: Unlike traditional forecasting models, it effectively handles complex relationships and large datasets.
AI Automates SQL & Forecasting: Users don’t need to spend a lot of time writing SQL or ML code—just ask a question, and the system does everything.
Interactive Insights: Powerful yet easy-to-understand insights.
The system can be adjusted, customized, and expanded to meet the company's needs.
