# Oil Well Profit Optimization – OilyGiant

## Project Overview
OilyGiant is an oil extraction company planning to develop **200 new oil wells**. The key challenge is selecting the region that offers the **highest expected profit while maintaining acceptable risk levels**.

This project uses machine learning and statistical techniques to predict oil reserves, estimate potential profits, and assess financial risk using bootstrapping. The final decision is based on both **profitability and risk constraints**.

## Objective
The main objectives of this project are to:
- Predict oil reserve volumes using machine learning.
- Select the most profitable oil wells within each region.
- Estimate expected profits under real business constraints.
- Evaluate financial risk using bootstrapping.
- Choose the optimal region with the highest average profit and loss risk below 2.5%.

## Dataset
Geological exploration data is provided for **three regions**, each stored in a separate CSV file:
- `geo_data_0.csv`
- `geo_data_1.csv`
- `geo_data_2.csv`

Each dataset contains:
- `id`: unique oil well identifier
- `f0`, `f1`, `f2`: geological features
- `product`: oil reserves (thousands of barrels)

## Business Constraints
- Only **Linear Regression** is allowed for modeling.
- 500 wells are evaluated per region.
- Only the **top 200 wells** are selected for development.
- Total investment budget: **$100 million**.
- Revenue per barrel: **$4.5 USD**.
- Revenue per unit (1,000 barrels): **$4,500 USD**.
- Regions with loss risk above **2.5%** must be rejected.

## Modeling Approach
- Split data into training and validation sets (75:25).
- Train a linear regression model for each region.
- Evaluate model performance using RMSE.
- Store predictions and true values for validation datasets.
- Compare predicted average reserves across regions.

## Profit Calculation
- Selected the 200 wells with the highest predicted reserves in each region.
- Calculated total expected profit based on predicted reserves.
- Compared average reserves with the minimum break-even threshold.
- Stored predicted values for further risk analysis.

## Risk Analysis (Bootstrapping)
- Applied bootstrapping with 1,000 samples per region.
- Generated profit distributions for each region.
- Calculated:
  - Average profit
  - 95% confidence interval
  - Probability of losses (negative profit)
- Identified regions with acceptable risk levels (< 2.5%).

## Final Recommendation
Based on:
- Expected average profit
- Confidence intervals
- Loss probability

The region with the **highest average profit and acceptable risk level** was selected as the optimal choice for oil well development. The final recommendation is fully supported by statistical and business-driven analysis.

## Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Bootstrapping techniques
- Jupyter Notebook

## Business Value
This project helps OilyGiant:
- Minimize financial risk in large-scale investments.
- Make data-driven decisions under uncertainty.
- Balance profitability and risk effectively.
- Apply machine learning to real-world resource allocation problems.

The project demonstrates an end-to-end analytical workflow combining machine learning, statistics, and business decision-making.
