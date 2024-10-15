# Construction Project Analysis with Machine Learning

## Project Overview
This project applies Six Sigma principles to the analysis of a simulated construction dataset. By following the DMAIC (Define, Measure, Analyze, Improve, Control) approach, we aim to predict the final cost of construction projects and classify project completion outcomes, ultimately driving efficiency, reducing variability, and minimizing cost overruns in project management.

### Define Phase
Construction companies often face the challenges of budget overruns and project delays, which negatively impact profitability. The goals of this analysis are:
1. **Predict the final cost** of construction projects using data on project phases, material costs, labor costs, and other relevant factors.
2. **Classify project completion**, determining whether a project will be completed successfully based on variables such as supply risks, delays, and change orders.

By leveraging data-driven insights, construction companies can improve decision-making around cost estimation, risk mitigation, and resource allocation.

### Measure Phase
In the Measure phase, we work with a simulated dataset containing 1000 project records. This dataset includes the following fields:
- `Project_ID`: Unique identifier for each project.
- `Task_ID`: Task identifier within the project.
- `Phase`: The current phase of the project (e.g., Planning, Foundation, Structure, etc.).
- `Material_Cost`: The cost of materials used in the project (in USD).
- `Labor_Cost`: The cost of labor for the project (in USD).
- `Material_Supply_Risk`: Likelihood of supply issues for materials (0.01-0.99).
- `Supplier_Reliability`: A score reflecting the reliability of suppliers (0.70-1.00).
- `Delay_Days`: The number of days the project has been delayed.
- `Weather_Risk`: The risk of weather disruption affecting the project (0.1-0.9).
- `Change_Orders`: The number of change requests made by the client.
- `Project_Completed`: A binary variable indicating whether the project was completed (1) or not (0).
- `Final_Cost`: The final cost of the project, calculated as the sum of material and labor costs, with additional costs for delays and change orders.

### Analyze Phase
In the Analyze phase, machine learning models are applied to uncover insights and identify key factors impacting project outcomes. These models include:

1. **Predicting Final Cost**:
   - A **Random Forest Regressor** was trained using features such as `Material_Cost`, `Labor_Cost`, `Delay_Days`, and `Supplier_Reliability`.
   - The model was evaluated using **Mean Absolute Error (MAE)** and the **R² Score**. It achieved an **R² Score** of **0.969**, with an average error of **$3,171** per project.

2. **Classifying Project Completion**:
   - A **Logistic Regression** classifier was trained to predict project completion.
   - It achieved an **Accuracy** of **52.67%**, with a **Precision** of **48.70%**, a **Recall** of **40.29%**, and an **F1 Score** of **44.09%**.

### Improve Phase
In the Improve phase, the insights gained from the analysis can be used to drive significant improvements in project cost estimation and risk management.

- **Cost Savings**: With the Random Forest model predicting project costs to within **$3,171** of the actual cost, companies could significantly reduce unexpected cost overruns. If a company typically spends $500,000 per project, a reduction in error by even **1%** (equivalent to **$5,000** per project) could result in significant savings.

- For example, with 100 projects per year, if the company avoids **5%** of cost overruns on each project through better planning and resource allocation, the total savings would amount to:
- 
   100 projects * 5,000 (1% per project) = $500,000 
   
   This estimation assumes that predictive models help in catching and mitigating cost escalations early in the process.

- **Risk Mitigation**: The classification model can identify **40%** of projects at risk of not being completed. Early identification of potential delays can enable proactive adjustments, saving further costs related to penalties or idle resources.

### Control Phase
To sustain these improvements, construction companies can implement continuous monitoring systems using these machine learning models to consistently predict project costs and completion likelihood. This data-driven approach, when fully integrated into operations, ensures that projects remain on track and budgets are more accurately controlled.

### Conclusion
By following the Six Sigma DMAIC methodology and implementing machine learning models, construction companies stand to save substantial amounts annually. Predictive models can enhance decision-making by reducing uncertainty around costs and completion timelines, ultimately improving profitability, reducing waste, and leading to more successful projects.

### Estimated Financial Impact:
Adopting these models could save the company **$500,000** annually by minimizing project overruns and reducing risk. These savings come from:
- Improved cost estimation with a **1-5%** reduction in project cost overruns.
- Proactive risk mitigation leading to fewer project delays and better resource management.

---



### Requirements
- pandas
- numpy
- scikit-learn
