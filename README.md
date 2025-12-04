# Public Transport Journey Analysis and Forecast


This document outlines key insights derived from historical public transport journey data and presents future forecasts generated using the Prophet time-series model.

---

## Key Insights

### 1. Post-Pandemic Travel Volatility
* **Surge (2022-2023):** Travel increased drastically by **25.05%**, adding to a previous growth of 16.39% (2021-2022).
* **Correction (2023-2024):** A sharp reduction of **23%** occurred, normalizing figures closer to the historical mean.

### 2. Route Preferences
* **High Demand:** People prefer **Rapid Routes**, followed by **Local Routes**.
* **Low Demand:** There is a tendency to avoid **Peak Service** routes.

### 3. Impact of COVID-19
* **2020:** Immediate lockdown restrictions caused an **81.55%** decrease from March to April.
* **2021:** The second wave and subsequent reopenings caused volatility: a **47.73%** decrease (July-Aug) followed by a **73.15%** drop (Aug-Sept).

### 4. Weekly Patterns
* **Weekdays:** Travel is highest (Tuesday-Wednesday), ranging **27% to 29% above average**.
* **Weekends:** Travel drops significantly, ranging **53% to 67% below average**.

### 5. School Route Seasonality
* **Observation:** A clear trend of increased usage in **May**, likely correlated with the exam season.

---

## Methodology: Why Prophet?

We utilized **Prophet** for forecasting due to its specific strengths with this dataset:
1.  **Multiple Seasonalities:** Capable of modeling daily, weekly, and yearly patterns simultaneously.
2.  **Robustness:** Handles outliers (like COVID-19 drops) and missing data without requiring manual imputation.
3.  **Trend Flexibility:** Identifies "change points" to adapt to shifting trends rather than assuming linearity.
4.  **Interpretability:** Decomposes forecasts into trend, seasonality, and holiday components.

---

## Forecast Data (October 2024)

### Data Legend
* **ds:** Date stamp.
* **yhat:** Predicted value (passenger count).
* **yhat_lower:** Lower bound of the confidence interval.
* **yhat_upper:** Upper bound of the confidence interval.

### 1. Local Route
| ds | yhat | yhat_lower | yhat_upper |
| :--- | :--- | :--- | :--- |
| 2024-09-30 | 10605.08 | 6862.05 | 14837.32 |
| 2024-10-01 | 12400.98 | 8693.86 | 16601.96 |
| 2024-10-02 | 12566.12 | 8577.26 | 16683.57 |
| 2024-10-03 | 12416.43 | 8462.63 | 16560.92 |
| 2024-10-04 | 11887.68 | 7926.91 | 15939.76 |
| 2024-10-05 | 2740.38 | -1457.53 | 6407.42 |
| 2024-10-06 | 1816.00 | -2120.97 | 6117.99 |

### 2. Light Rail
| ds | yhat | yhat_lower | yhat_upper |
| :--- | :--- | :--- | :--- |
| 2024-09-30 | 7590.65 | 5209.74 | 9919.17 |
| 2024-10-01 | 8644.52 | 6349.86 | 10988.40 |
| 2024-10-02 | 8687.11 | 6246.58 | 10987.83 |
| 2024-10-03 | 8606.40 | 6579.51 | 10873.71 |
| 2024-10-04 | 8636.38 | 6438.69 | 10946.70 |
| 2024-10-05 | 5172.36 | 2948.39 | 7529.89 |
| 2024-10-06 | 3814.68 | 1369.08 | 6121.89 |

### 3. Peak Service
| ds | yhat | yhat_lower | yhat_upper |
| :--- | :--- | :--- | :--- |
| 2024-09-30 | 224.44 | 123.02 | 333.16 |
| 2024-10-01 | 269.88 | 165.55 | 370.85 |
| 2024-10-02 | 269.66 | 164.98 | 368.70 |
| 2024-10-03 | 243.11 | 137.50 | 349.78 |
| 2024-10-04 | 191.46 | 82.23 | 290.75 |
| 2024-10-05 | -10.42 | -118.94 | 85.61 |
| 2024-10-06 | -9.03 | -110.26 | 92.98 |

### 4. Rapid Route
| ds | yhat | yhat_lower | yhat_upper |
| :--- | :--- | :--- | :--- |
| 2024-09-30 | 13476.17 | 8720.70 | 17788.75 |
| 2024-10-01 | 15584.18 | 10933.88 | 20170.14 |
| 2024-10-02 | 15672.12 | 10818.92 | 20138.99 |
| 2024-10-03 | 15483.70 | 10668.51 | 20114.25 |
| 2024-10-04 | 14777.96 | 9967.87 | 19405.69 |
| 2024-10-05 | 6592.79 | 2149.47 | 11209.27 |
| 2024-10-06 | 5144.67 | 714.21 | 9522.05 |

### 5. School Route
| ds | yhat | yhat_lower | yhat_upper |
| :--- | :--- | :--- | :--- |
| 2024-09-30 | 1417.82 | -537.41 | 3387.13 |
| 2024-10-01 | 1842.16 | -70.36 | 3832.72 |
| 2024-10-02 | 1902.88 | 51.71 | 3717.38 |
| 2024-10-03 | 1805.43 | -139.29 | 3776.81 |
| 2024-10-04 | 1623.43 | -248.06 | 3626.38 |
| 2024-10-05 | -1416.06 | -3466.25 | 444.24 |
| 2024-10-06 | -1307.48 | -3309.21 | 699.21 |

### 6. Other Route
| ds | yhat | yhat_lower | yhat_upper |
| :--- | :--- | :--- | :--- |
| 2024-09-30 | 51.33 | 9.94 | 91.44 |
| 2024-10-01 | 59.43 | 18.94 | 102.22 |
| 2024-10-02 | 63.71 | 26.20 | 106.00 |
| 2024-10-03 | 66.41 | 24.16 | 108.71 |
| 2024-10-04 | 63.46 | 22.32 | 103.63 |
| 2024-10-05 | 28.15 | -11.49 | 69.09 |
| 2024-10-06 | 27.95 | -11.20 | 66.90 |
