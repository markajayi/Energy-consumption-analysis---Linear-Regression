# 🏠 Energy Consumption Dataset: Linear Regression

https://www.google.com/imgres?q=electrical%20power%20system&imgurl=https%3A%2F%2Fvitalconcon.com%2Fwp-content%2Fuploads%2F2017%2F04%2F18.jpg&imgrefurl=https%3A%2F%2Fvitalconcon.com%2Findex.php%2Fservices%2Felectrical-power-system-engineering%2F&docid=kIz48kCn1jr_4M&tbnid=ZmOmNjTgyDs9jM&vet=12ahUKEwiY1p7O262QAxUEQUEAHSuGFUMQM3oECDYQAA..i&w=848&h=477&hcb=2&ved=2ahUKEwiY1p7O262QAxUEQUEAHSuGFUMQM3oECDYQAA

## 🎯 Project Title

**Energy Consumption Dataset: Linear Regression**

## 💡 Project Goal

The primary objective of this project was to build a highly predictive **Multiple Linear Regression Model** to estimate daily or hourly energy consumption. The model specifically focuses on quantifying the relationship between consumption and a mix of **environmental factors** (e.g., temperature) and **building characteristics** (e.g., property type and square footage).

The final goal was to develop a validated, stable equation that achieves a high degree of predictive accuracy ($\mathbf{\text{R}^2 \approx 0.909}$) and provides clear, actionable insights for energy efficiency and operational management.

## 🛠️ Model Development and Validation Process

The final reliable model was achieved through systematic diagnosis and correction of initial statistical issues:

### 1. Data Leakage Resolution

* **Problem:** The initial model run resulted in an unrealistic $\text{R}^2$ of $1.00$.

* **Correction:** The variable `Appliances Us` was identified and removed as a source of **data leakage**, as it was too closely related to the outcome. This established a credible baseline $\text{R}^2$ of $0.909$.

### 2. Multicollinearity Correction (Dummy Variable Trap)

* **Problem:** Including all three property type dummy variables (`Residential`, `Commercial`, `Industrial`) created perfect collinearity with the intercept, resulting in calculation errors in the summary output.

* **Correction:** The `Industrial` variable was removed. This established **Industrial** as the necessary **reference category**, resolving the multicollinearity and stabilizing the model.

## 🔬 Final Model Results and Key Insights

The final model uses 6 independent predictors and is highly significant ($\text{R}^2 = 0.909144$).

### Final Regression Equation

The equation for predicting energy consumption in any property:

$$
\begin{align*} \text{Energy Consumption} = &\ 3065.503 \\ &- 1016.55 \times (\text{Residential}) \\ &- 501.385 \times (\text{Commercial}) \\ &+ 0.049762 \times (\text{Square Footage}) \\ &+ 10.23883 \times (\text{Number of Oc}) \\ &- 7.46471 \times (\text{Average Temper}) \\ &+ 56.06374 \times (\text{Weekday}) \end{align*}
$$

### Actionable Insights

| Driver Category | Key Finding | Strategic Implication |
| :--- | :--- | :--- |
| **Building Type** | **Industrial** is the highest consumer (baseline). | Prioritize efficiency budgets for deep retrofits in the Industrial sector. |
| **Environmental Factor** | **Average Temperature** has a strong $\mathbf{-7.46}$ coefficient. | **Heating** is the dominant energy drain. Focus interventions on insulation and thermal controls. |
| **Building Characteristic** | $\text{Square Footage}$ and $\text{Number of Oc}$ are significant positive drivers. | Focus management protocols on optimizing energy use based on scale and actual occupancy levels. |
| **Operational Factor** | Consumption is $\mathbf{56.06}$ units higher on a **Weekday**. | Implement strict, automated shutdown/setback protocols for all weekend and holiday periods. |

## 💻 Repository Structure and Usage

| File/Folder | Description |
| :--- | :--- |
| `data/` | Contains the raw and cleaned energy consumption dataset. |
| `analysis_output/` | Contains the final Excel regression summary and diagnostic outputs. |
| `README.md` | This file: Documentation of the project and model specification. |

### Replication Instructions

To replicate the final model:

1.  Use the data from the `data/` folder.

2.  Run a multiple linear regression with **Energy Consumption** as the dependent variable.

3.  Ensure only the **6 specified predictors** are included (excluding `Appliances Us` and `Industrial`).

## 🙋 Contact

* **Author:** Ajayi Mark Enesi

* **Email:** markajayi17@gmail.com
