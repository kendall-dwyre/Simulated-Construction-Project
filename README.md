# Construction Project Analysis with Machine Learning

## Project Overview
This project applies Six Sigma principles to the analysis of a simulated construction dataset. By following the DMAIC (Define, Measure, Analyze, Improve, Control) approach, we aim to predict the final cost of construction projects and classify project completion outcomes, ultimately driving efficiency and reducing variability in project management processes.

### Define Phase
In the Define phase, we clearly articulate the problem we are solving: construction companies often face cost overruns and project delays, which negatively impact profitability. Our goals are:
1. **Predict the final cost** of construction projects using data on project phases, material costs, labor costs, and other relevant factors.
2. **Classify project completion**, determining whether a project will be completed successfully based on known variables such as supply risks, delays, and change orders.

### Measure Phase
During the Measure phase, we collect relevant data. The simulated dataset consists of 1000 records and contains the following fields:
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
In the Analyze phase, we apply machine learning models to uncover insights and identify key factors impacting project outcomes.

1. **Predicting Final Cost**:
   - A **Random Forest Regressor** was trained using features such as `Material_Cost`, `Labor_Cost`, `Delay_Days`, and `Supplier_Reliability`.
   - The model was evaluated using **Mean Absolute Error (MAE)** and the **R² Score**. It achieved an **R² Score** of **0.969**, with an average error of **$3,171**.

2. **Classifying Project Completion**:
   - A **Logistic Regression** classifier was trained to predict project completion.
   - It achieved an **Accuracy** of **52.67%**, with a **Precision** of **48.70%**, a **Recall** of **40.29%**, and an **F1 Score** of **44.09%**. While these results show moderate performance, opportunities exist for improvement through further refinement of the model or additional data.

### Improve Phase
In the Improve phase, we leverage the findings from the Analyze phase to enhance business processes. 
- **Cost Management**: The predictive model for final costs can help reduce cost overruns by allowing project managers to forecast budget needs more accurately and make data-driven decisions on resource allocation.
- **Risk Mitigation**: The classification model helps identify potential project delays early, allowing managers to take corrective action and minimize the impact of disruptions such as supply risks and weather.

### Control Phase
To sustain the improvements, we can implement ongoing monitoring systems that use these machine learning models to continuously predict project costs and completion likelihood. Automating these processes ensures that the insights remain actionable throughout the project lifecycle, maintaining Six Sigma levels of control over variance in project outcomes.

### Conclusion
By following Six Sigma's DMAIC methodology, this project demonstrates how data-driven approaches can optimize construction management. Predictive models enhance decision-making by reducing uncertainty around costs and completion timelines, ultimately improving profitability and efficiency for construction companies.

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
"""

# Save to a file
file_path = "/mnt/data/README.md"
with open(file_path, "w") as f:
    f.write(content)

file_path
