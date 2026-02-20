# Revenue Analysis using multiple regression model

#### Project Overview
**Goal:** Use transaction-level data to define Revenue as the target and identify relevant independent variables.
* **1.** Perform statistical inference using statsmodels OLS to understand variable significance, direction, and impact on revenue.
* **2.** Select and refine features based on statistical and business relevance.
* **3.** Build a regression model using scikit-learn to estimate revenue for unseen transactions.
* **4.** Evaluate performance using R² and error metrics and interpret results for business decisions.


#### Model Metrics Interpretation

* **R-squared (R²): 0.960880**
* The model explains approximately 96.09% of the variance in revenue in the test data. The train $R^2$ of 0.960281 (96.0%) is very close to the test value, indicating strong generalization and minimal overfitting.

* **Mean Absolute Error (MAE): 0.21** 
* On average, the model's log-revenue predictions are off by only 0.21 units. As seen in the plot of actual vs Estimated revenue, the model is good at capturing the relationship between features and revenue, which is useful for business planning

* **Mean Squared Error (MSE): 0.07** — The low MSE of both test (0.078398) and train (0.078911) shows the model is stable and is not being distorted by large prediction errors.


#### Model Mertics Interpretation with Business Context

* **Coefficients Interpretation in Business Context:**
    The large coefficients for Electronics (2.687440), Home & Garden (1.773539), and Sports (1.447101) suggest these categories have a strong positive impact on revenue, indicating that focusing on these categories is a key strategy for maximizing revenue.

* **MAE and RMSE Interpretation in Business Context:**
    In Business Scenario, If average revenue per transaction is around **$1208.71**
* **Typical Scenario (MAE):** For a predicted transaction of **$1,208.71**, the average error is **±$248.10**, resulting in a typical range of **$960.61** to **$1,456.81**.
* **High-Risk Scenario (RMSE):** For volatile transactions, the error range is **±$642.82**, creating a risk range of **$565.89** to **$1,851.53**..


### Business Implications

* **Strategic Focus:** Focus on high-revenue categories like Electronics, Home & Garden, and Sports for marketing and inventory strategies, as these show the highest positive coefficients.

* **Discount Optimization:** As shown earlier, the presence of a discount (has_discount) has a negative coefficient, and the dataset is dominated by low-value transactions. We can perform optimization by reducing the frequency of discounts on low-value products and selectively applying a discount flag to premium products; this could increase revenue contribution through higher quantities purchased in top tiers.

* **Fashion Category Growth:** In the Product Categories analyzed, we observed that Fashion has a low percentage discount allocation yet maintains a higher average unit price. Since the Fashion category has a strong positive coefficient, implementing strategies for this category would boost our revenue generation. Currently, we see overall lower discounts; by offering more strategic discounts, we could gain an advantage in revenue generation.

* **Margin Protection:** We observed in the Product Categories that Food and Books have negative coefficients, which means they make less of a contribution to revenue compared to other categories. Even though these two products are sold in higher quantities, reducing discounts here could boost overall revenue.


# Own Conclusion about model understanding

**Data Nature**
* Before building any model, we should understand how the numbers are actually created in the business. If we don’t know how the data is formed, the model may look accurate but still not reflect the real logic behind the numbers.

**Real-World variation and Balance**
* Even if current results look good, real-world outcomes are usually influenced by many visible and hidden factors. Adding more meaningful information helps represent reality better. Using L2 (Ridge) can reduce extreme dependence on a few strong factors and make the model more balanced and stable over time.
