# Data Dictionary

This document provides detailed descriptions of the datasets used in the **PowerCo Customer Churn Analysis** project. The data represents small and medium enterprise (SME) utility customers, covering historical consumption, contract attributes, pricing plans, and 3-month churn labels.

---

## 1. `client_data.csv` (Customer Profile & Consumption)

| Feature | Data Type | Description |
| :--- | :--- | :--- |
| `id` | String (Hash) | Unique client/company identifier. |
| `activity_new` | String (Hash) | Category of the company's business activity. |
| `channel_sales` | String (Hash) | Code of the sales channel through which the customer was acquired. |
| `cons_12m` | Float | Electricity consumption over the past 12 months (kWh). |
| `cons_gas_12m` | Float | Gas consumption over the past 12 months (kWh). |
| `cons_last_month` | Float | Electricity consumption in the last calendar month (kWh). |
| `date_activ` | Date (`YYYY-MM-DD`) | Date of initial contract activation. |
| `date_end` | Date (`YYYY-MM-DD`) | Registered contract end date. |
| `date_modif_prod` | Date (`YYYY-MM-DD`) | Date of the most recent modification to the customer's plan/product. |
| `date_renewal` | Date (`YYYY-MM-DD`) | Date of the upcoming/next contract renewal. |
| `forecast_cons_12m` | Float | Forecasted electricity consumption for the next 12 months. |
| `forecast_cons_year` | Float | Forecasted electricity consumption for the next calendar year. |
| `forecast_discount_energy` | Float | Forecasted value of the current energy discount. |
| `forecast_meter_rent_12m` | Float | Forecasted bill amount for meter rental over the next 12 months. |
| `forecast_price_energy_off_peak` | Float | Forecasted price of energy during the off-peak period (1st tier). |
| `forecast_price_energy_peak` | Float | Forecasted price of energy during the peak period (2nd tier). |
| `forecast_price_pow_off_peak` | Float | Forecasted power price during off-peak period. |
| `has_gas` | String (`t`/`f`) | Flag indicating whether the customer also subscribes to gas. |
| `imp_cons` | Float | Current invoiced/paid electricity consumption. |
| `margin_gross_pow_ele` | Float | Gross margin on power subscription. |
| `margin_net_pow_ele` | Float | Net margin on power subscription. |
| `nb_prod_act` | Integer | Total number of active products and services the client subscribes to. |
| `net_margin` | Float | Overall net profit margin across all products. |
| `num_years_antig` | Integer | Client antiquity / tenure (in years). |
| `origin_up` | String (Hash) | Marketing campaign or acquisition initiative code. |
| `pow_max` | Float | Subscribed maximum power limit (kW). |
| `churn` | Integer (`0`/`1`) | **Target Variable**: Has the client churned within the next 3 months (`1` = Churned, `0` = Retained). |

---

## 2. `price_data.csv` (Historical Pricing & Tariffs)

| Feature | Data Type | Description |
| :--- | :--- | :--- |
| `id` | String (Hash) | Unique client/company identifier (links to `client_data.csv`). |
| `price_date` | Date (`YYYY-MM-DD`) | Monthly reference date of pricing observation. |
| `price_off_peak_var` | Float | Variable energy price for Period 1 (Off-peak). |
| `price_peak_var` | Float | Variable energy price for Period 2 (Peak). |
| `price_mid_peak_var` | Float | Variable energy price for Period 3 (Mid-peak). |
| `price_off_peak_fix` | Float | Fixed power capacity fee for Period 1 (Off-peak). |
| `price_peak_fix` | Float | Fixed power capacity fee for Period 2 (Peak). |
| `price_mid_peak_fix` | Float | Fixed power capacity fee for Period 3 (Mid-peak). |

---

> **Note on Data Anonymization:** Categorical identifiers (e.g., `id`, `channel_sales`, `origin_up`, and `activity_new`) have been obfuscated using cryptographic hash functions to preserve customer privacy while retaining commercial variance and predictive power.
