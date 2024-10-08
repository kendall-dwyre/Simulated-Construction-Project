# Construction Project Analysis with Machine Learning

## Project Overview
This project involves a simulated dataset representing a construction company's project data. The dataset includes information on project phases, material costs, labor costs, supply risks, and various other features influencing the success and completion of construction projects. The goal of this analysis is twofold:
1. **Predict the final cost** of construction projects based on various factors.
2. **Classify project completion**, predicting whether a project will be completed based on available data.

### Dataset Description
The dataset is a simulated construction project dataset with 1000 records, containing the following fields:
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

### Analysis Process

1. **Data Preprocessing**: The dataset was first prepared by generating the `Final_Cost` variable, which combines material costs, labor costs, delay penalties, and client change orders to simulate the true cost of a construction project.

2. **Predicting Final Cost**: 
    - A **Random Forest Regressor** was trained using features such as `Material_Cost`, `Labor_Cost`, `Delay_Days`, `Supplier_Reliability`, and others to predict the final cost of each project.
    - The model was evaluated using the **Mean Absolute Error (MAE)** and the **R² Score**.
    - The **R² Score** was found to be **0.969**, indicating the model explained a significant portion of the variance in project costs, with an average error of around **$3,171**.

3. **Classifying Project Completion**:
    - A **Logistic Regression** classifier was trained to predict whether a project would be completed (binary classification).
    - The model used similar features as those for the cost prediction and was evaluated using **Accuracy**, **Precision**, **Recall**, and the **F1 Score**.
    - The model achieved an **Accuracy** of **52.67%**, with a **Precision** of **48.70%**, a **Recall** of **40.29%**, and an **F1 Score** of **44.09%**. These results indicate moderate performance in predicting project completion, with room for improvement.

### Insights from the Data

#### 1. **Predicting Final Costs**:
   - The ability to accurately predict project costs is crucial in construction management. The **Random Forest Regressor** performed well, with a high **R² Score** of **0.969**. This means the model is able to predict final costs with high accuracy using the available features.
   - **Material Costs** and **Labor Costs** were found to be the strongest predictors of the final cost, as expected, with delays and change orders adding variability to the final cost prediction.
   - Insights from this model can help construction managers plan budgets more effectively, mitigate the risks of cost overruns, and adjust resource allocation before it's too late.

#### 2. **Project Completion Classification**:
   - The Logistic Regression model showed moderate success in predicting whether a project would be completed based on factors like delays, material costs, and supplier reliability.
   - The **Recall** score (40.29%) shows that the model was able to identify around 40% of projects that were not completed, although improvements could be made to increase its accuracy.
   - This model could be enhanced with additional data or more complex algorithms, such as ensemble methods, to provide more actionable insights for stakeholders regarding project success likelihood.

### Why These Insights are Important
- **Cost Management**: Accurately predicting the final cost of projects helps businesses like Mammoth Built stay within budget and avoid unexpected financial strain. With data-driven predictions, project managers can make better decisions about when and how to allocate resources, secure materials, and manage labor costs.
  
- **Risk Mitigation**: Predicting whether a project is likely to be completed on time can provide early warnings for potential delays. This enables proactive measures to avoid penalties, improve supplier management, and address risks like weather disruptions.

- **Operational Efficiency**: Insights from both cost prediction and project completion modeling allow for more streamlined operations, minimizing wasted resources, and improving the overall profitability of the business.

### Conclusion
This project demonstrates the power of data science and machine learning in optimizing construction project management. By leveraging predictive models, construction companies can reduce uncertainty, manage risks, and improve their decision-making processes, ultimately leading to more successful and profitable projects.

---

## How to Run the Analysis

1. Clone the repository:
    ```bash
    git clone <repository-link>
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the analysis:
    You can execute the analysis in a Python environment by running the provided script:
    ```bash
    python construction_analysis.py
    ```

### Requirements
- pandas
- numpy
- scikit-learn
