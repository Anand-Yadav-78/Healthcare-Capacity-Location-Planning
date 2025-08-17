# **Healthcare-Capacity-Location-Planning**

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

This repository contains an end-to-end operations research project focused on optimizing healthcare resource allocation during a pandemic. The primary goal is to use prescriptive analytics to determine the optimal placement and capacity of temporary COVID-19 treatment facilities to satisfy all patient demand while minimizing total system-wide costs.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **📋 Problem Statement**
During a public health crisis like the COVID-19 pandemic, healthcare systems face unprecedented strain, often leading to capacity shortages. The critical challenge for officials is to decide where to build temporary facilities and how to allocate patients to them efficiently. This project tackles this logistical problem by creating a data-driven model that provides a clear, optimal strategy for expanding capacity, moving beyond reactive measures to enable proactive and cost-effective planning.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **📊 Data Summary**
The analysis is based on a set of parameters for a healthcare network of nine counties, each with forecasted demand for COVID-19 treatment. The data includes:

County Data: Geographic coordinates and forecasted patient demand for each of the nine counties.

Existing Facility Data: Locations and treatment capacities of 14 permanent healthcare facilities.

Temporary Facility Data: Locations and potential capacities for 9 proposed temporary facilities.

Financial Data: A cost structure including a fixed cost of \$500,000 to build a temporary facility and a variable patient travel cost of \$5 per 10 miles.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **🛠️ Methodology & Techniques**
To find the provably optimal solution, a Mixed-Integer Programming (MIP) model was formulated and solved. This mathematical optimization approach is ideal for facility location problems involving both discrete and continuous decisions.

Model Formulation: The business problem was translated into a formal mathematical model with three core components:

Decision Variables: Including binary variables (y_t) to decide whether to build a temporary facility, and continuous variables (x_c,f) to determine the number of patients allocated from a county to a facility.

Objective Function: A linear equation designed to minimize total costs, calculated as (Total Patient Driving Costs) + (Total Fixed Costs of Building Facilities). A large penalty was included for adding emergency capacity to ensure it is only used as a last resort.

Constraints: A series of linear equations encoding the system's rules, such as ensuring all patient demand is met and that no facility's capacity is exceeded.

Solving: The model was implemented in Python using the Gurobi (gurobipy) solver, a high-performance, industry-standard tool for mathematical optimization.

Scenario Analysis: The model's robustness and strategic value were tested by running two distinct scenarios:

A base scenario with the initial forecasted demand.

A high-demand scenario with a 20% increase in patient numbers to simulate a surge and test the system's resilience.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **🚀 Tools and Libraries**
This project was built using Python and the following core libraries:

Gurobi (gurobipy): A powerful, commercial-grade solver for building and solving the mixed-integer programming model.

itertools: To assist in creating the combinations of counties and facilities needed for the model's variables and constraints.

math: For distance calculations.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **💡 Inference and Conclusion**
The optimization model produced clear, data-driven recommendations for both planning scenarios.

Base Scenario: The optimal solution was to build three new temporary facilities (at locations 15, 17, and 18) for a total minimum cost of \$1.52 million. This plan successfully meets all patient demand.

High-Demand Scenario: With a 20% demand increase, the model recommended building all nine potential temporary facilities and adding emergency capacity at two of them. The massive penalty cost incurred in the objective function signaled a critical system failure, indicating that the planned temporary capacity is insufficient to handle such a surge.

The key insight is that the model not only provides a cost-effective plan for a given forecast but also quantifies the system's breaking point, offering a powerful tool for risk assessment and contingency planning.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **Final Conclusion:**
This project successfully demonstrates the strategic value of Mixed-Integer Programming for public health logistics. The model's output is a direct, actionable plan that replaces subjective decision-making with a quantitative framework. It provides concrete answers to "how many" and "where," enabling leaders to make informed decisions about infrastructure investment. By running different scenarios, the model serves as a vital decision-support tool, highlighting system vulnerabilities and allowing public health officials to develop more robust and resilient pandemic response strategies.
