[eda-readme.md](https://github.com/user-attachments/files/31261971/eda-readme.md)
# Supply-chain-eda-project
Exploratory Data Analysis of FedEx logistics data to identify bottlenecks, optimize logistics processes, and improve cost and delivery efficiency.
# Exploratory Data Analysis on FedEx Logistics Data

## Project Overview

This project presents a comprehensive **Exploratory Data Analysis (EDA)** of a FedEx logistics and supply chain dataset containing **10,324 shipment records across 33 variables**.

The objective of the analysis was to understand shipment behavior, identify supply chain bottlenecks, evaluate vendor and shipment performance, investigate the drivers of logistics costs and delivery delays, and develop actionable recommendations for improving **operational efficiency, delivery reliability, and transportation cost efficiency**.

The analysis covers shipment modes, vendors, countries, fulfillment methods, INCO terms, lead times, freight costs, insurance costs, shipment characteristics, and delivery performance. A total of **31 visualizations and analytical comparisons** were used to identify patterns and relationships within the data.

---

## Project Objectives

The analysis was conducted to:

* Identify bottlenecks across the supply chain.
* Understand shipment behavior and vendor reliability.
* Analyze factors affecting lead times, freight costs, and delivery performance.
* Identify opportunities to improve operational efficiency.
* Improve delivery reliability and predictability.
* Identify opportunities to reduce logistics and transportation costs.
* Provide data-driven insights to support strategic and operational decision-making.

---

## Dataset

The dataset contains **10,324 shipment records and 33 variables**, covering information related to:

* Shipment and delivery details
* Vendors and manufacturing sites
* Countries and destinations
* Shipment modes
* Shipment weight and quantity
* Freight and insurance costs
* Molecules and test types
* Product group and Sub groups
* Dosage forms and brands
* Vendor INCO terms
* Fulfillment methods
* Planned lead times
* Delivery status
* Delivery delay

---

## Tools & Technologies

* **Python**
* **Pandas** – Data cleaning, transformation, aggregation, and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization
* **Google Colab** – Development environment
* **Decision Tree Models** – Feature importance analysis

---

# Analysis Performed

## 1. Data Cleaning & Preparation

The dataset was examined for structural, missing-value, categorical, and data-quality issues before conducting the analysis.

Key preparation steps included:

* Examining the dataset structure, dimensions, data types, and variable distributions.
* Identifying missing values and investigating their patterns and potential impact on the analysis.
* Investigating inconsistent and non-standard categorical values and creating cleaned categorical variables where required.
* Converting date variables into appropriate date formats and calculating relevant time-based measures.
* Creating derived variables for:

  * Planned lead time
  * Delivery status
  * Delivery delay
  * Freight cost per kg
  * Insurance percentage
  * Insurance cost per kg
* Investigating unusual observations, negative delivery delays, and other potential data-quality issues.
* Examining missing **Shipment Mode**, **Dosage**, **Line Item Insurance**, and **PO Sent to Vendor Date** values and considering their implications before using these variables in analysis.
* Identifying records where shipment weight was unavailable and using separately captured weight information where appropriate.
* Reviewing grouping and descriptive summary statistics for freight cost, insurance, shipment mode, vendor, country, and other key variables to support subsequent visualizations and analysis.

---

## 2. Shipment Volume & Shipment Mode Analysis

Shipment modes were compared based on shipment volume, freight cost, delivery performance, and delay rates.

The analysis included:

* Air
* Air Charter
* Truck
* Ocean
* Other/unassigned shipment modes

This helped identify the trade-off between **transportation cost and delivery performance** across different shipment modes.

---

## 3. Vendor Performance Analysis

Vendors were evaluated based on:

* Shipment volume
* Delivery delay rate
* Planned lead time
* Country coverage
* Freight cost

High-volume vendors were examined separately from low-volume vendors to avoid interpreting shipment counts without considering the underlying shipment volume.

---

## 4. Country-Level Analysis

Countries were compared based on:

* Shipment volume
* Delivery delay rates
* Number of delayed shipments
* Freight cost per kg
* Delivery delay duration

The analysis distinguished between **the number of delayed shipments, the proportion of shipments that were delayed, and the severity of delays**, since these metrics can identify different operational issues.

---

## 5. Freight Cost Analysis

Freight costs were analyzed in relation to:

* Shipment mode
* Country
* Vendor INCO Term
* Fulfillment method
* Vendor

Freight cost per kg was also examined across countries to identify locations with unusually high transportation costs.

---

## 6. Lead Time Analysis

Planned lead time was analyzed to understand the overall distribution of expected shipment durations.

The distribution was approximately bell-shaped with a slight right skew. Extreme lead-time observations were also identified for further investigation.

---

## 7. Delivery Delay Analysis

Delivery performance was analyzed from two different perspectives:

### Occurrence of Delay

This examines **whether a shipment was delayed or not**.

### Extent of Delay

This examines **how many days a shipment was delayed once a delay occurred**.

This distinction was important because the factors associated with the occurrence of a delay were not necessarily the same as those associated with the severity of the delay.

---

## 8. Insurance Cost Analysis

Line Item Insurance was analyzed across:

* Shipment modes
* Line Item Quantity
* Country

The analysis also examined the relationship between insurance cost and shipment weight.

---

# Key Findings

## Shipment Mode

* **Air is the most frequently used shipment mode** and has the highest freight cost among the major assigned shipment modes.
* **Air is also associated with faster delivery**, making it useful where delivery speed is a priority.
* **Ocean is the lowest-cost shipment mode, followed by Truck.**
* **Truck has a relatively high proportion of delayed deliveries**, making its lower transportation cost less attractive when delivery reliability is considered.
* **Air Charter provides a potential balance between cost and delivery performance**, with lower freight cost than Air and better delivery performance than Truck and Ocean.
* Shifting a suitable portion of Air shipments to Air Charter could reduce transportation costs, while shifting selected high-delay Truck shipments to Air Charter could potentially improve delivery performance.

---

## Vendor Performance

* **SCMS RDC accounts for a very large proportion of shipments** and also has a relatively high proportion of delayed deliveries.
* Other vendors showing delivery-performance concerns include **Orgenics, Aurobindo Pharma, and CIPLA Ltd.**
* SCMS RDC also has a relatively high planned lead time, indicating that a longer planned lead time does not necessarily translate into better delivery performance.
* Several lower-delay vendors, including **Trinity Biotech, AbbVie Laboratories, Mylan Labs, and Hetero Labs**, demonstrated relatively consistent delivery performance across multiple destinations.
* Vendor diversification may therefore provide an opportunity to reduce dependence on high-volume vendors with weaker delivery performance, subject to capacity, quality, and supply requirements.

---

## Country-Level Performance

* **Burundi has the highest proportion of delayed deliveries**, followed by **Togo and Senegal**.
* The countries with the highest **number of delayed shipments** are not necessarily the same as those with the highest **delay rates**, highlighting the importance of considering shipment volume when interpreting country performance.
* **Guinea and Pakistan have considerably higher median Freight Cost per Kg** compared with many other countries, making them potential priorities for further cost investigation.
* The extent of delivery delay varies considerably across countries, indicating that country-specific logistics conditions may contribute to the severity of delays.
* Country-level investigation is therefore important when addressing severe or prolonged delivery delays.

---

## Freight Cost

* Freight cost is influenced more strongly by **shipment mode and fulfillment-related factors than by shipment weight alone**.
* Freight cost per kg varies considerably across countries.
* **Country and Vendor INCO Term were the strongest predictors of Freight Cost per Kg** in the Decision Tree analysis.
* Molecule/Test Type and Manufacturing Site also contributed to the prediction of Freight Cost per Kg.
* This suggests that reducing shipment weight alone may not be the most effective approach to controlling transportation costs.
* Greater cost-optimization opportunities may exist through **shipment mode, fulfillment method, vendor, country, and INCO-term optimization**.

---

## Delivery Delay

The analysis identified different factors associated with **whether a shipment was delayed** versus **how severe the delay was**.

### Occurrence of Delay

The Decision Tree analysis identified:

* **Vendor INCO Term** as the most influential feature.
* Shipment Mode as the second most influential feature.
* Shipment Weight and Country as additional important features.

### Extent of Delay

For shipments that experienced delays:

* **Country** was the strongest feature.
* Shipment Weight was the second most influential feature.
* Vendor INCO Term also contributed substantially.

This indicates that **the factors influencing delay occurrence and delay severity are different**. Vendor INCO Term appears more important in predicting whether a delay occurs, while Country is more important in explaining the extent of the delay once it occurs.

---

## Fulfillment Method & INCO Terms

* Shipments fulfilled through **RDC**, which generally have no recorded INCO term, show a relatively high delay rate of approximately **17%**.
* Certain INCO terms such as **CIF, CIP, and DAP showed 100% on-time delivery**, but these categories had relatively low shipment frequencies and therefore should not automatically be considered superior based solely on this result.
* **DDP showed a lower delay rate than RDC-related shipments**, while EXW and DDP arrangements also presented potential cost-efficiency opportunities when considered alongside fulfillment method.
* Increasing **Direct Drop fulfillment**, where operationally feasible, may provide opportunities to improve both delivery and freight-cost efficiency.

---

## Insurance Cost

* Insurance cost shows only a **weak positive relationship with shipment weight**, with substantial variation even among shipments with similar weights.
* **Shipment Mode was the strongest predictor of Line Item Insurance**, followed by Line Item Quantity in the Decision Tree analysis.
* Air Charter showed the **highest median insurance cost** among the shipment modes analyzed.
* However, insurance cost contributes substantially less to overall logistics costs than freight cost.
* Therefore, shipment mode decisions should not be based on insurance cost alone. Insurance should be considered alongside **freight cost and delivery performance**.
* Despite its higher median insurance cost, Air Charter can still be considered a potential cost-efficient alternative to Air because freight cost has a much greater impact on overall logistics cost.

---

# Business Recommendations

## 1. Optimize Shipment Mode

Since Air is the most expensive major shipment mode and Truck has a relatively high delay rate, the client should evaluate opportunities to shift suitable shipments from **Air and Truck to Air Charter**.

Air Charter can provide a balance between transportation cost and delivery performance. Replacing some Air shipments with Air Charter could help offset the additional cost of moving selected Truck shipments to Air Charter.

---

## 2. Diversify & Optimize Vendor Allocation

The client should consider reducing excessive dependence on high-volume vendors with relatively poor delivery performance.

Where feasible, shipment allocation can be diversified toward better-performing vendors such as:

* Trinity Biotech
* AbbVie Laboratories
* Mylan Labs
* Hetero Labs

Any increase in vendor allocation should be evaluated against **capacity, quality, supply requirements, and destination coverage**.

---

## 3. Review Fulfillment Strategy & INCO Terms

RDC-related shipments show a relatively high delay rate and generally have no recorded INCO term.

Where operationally feasible, the client should evaluate increasing **Direct Drop fulfillment**, particularly where suitable EXW and DDP arrangements can be implemented.

This may help improve both **delivery efficiency and freight-cost efficiency**.

---

## 4. Consider Country-Specific Logistics Factors

Since Country was the strongest predictor of the **extent of delivery delay**, countries experiencing severe delays should be investigated individually.

Potential areas for investigation include:

* Local logistics conditions
* Transportation routes
* Vendors
* Manufacturing sites
* Shipment modes
* INCO terms
* Fulfillment methods

Country-specific strategies may therefore be more effective than applying a single solution across all destinations.

---

## 5. Improve Freight Cost Efficiency

Since freight cost is more strongly associated with shipment mode, country, INCO terms, and fulfillment-related factors than shipment weight alone, cost optimization should focus on these controllable logistics factors.

Potential actions include:

* Shifting suitable Air shipments toward Air Charter.
* Replacing selected high-delay Truck shipments with Air Charter.
* Evaluating alternative vendors and manufacturing sites.
* Increasing Direct Drop fulfillment where feasible.
* Reviewing high-cost countries and their associated shipment configurations.
* Optimizing suitable INCO terms.

---

## 6. Review Insurance Costs in Context

Insurance should be monitored, but it should not be treated as the primary logistics cost optimization lever because its contribution to overall logistics cost is substantially lower than freight cost.

Shipment mode has a stronger association with insurance cost, but decisions should be based on the **combined impact of insurance, freight cost, and delivery performance**.

---

# Conclusion

The EDA provided a comprehensive understanding of **shipment behavior, vendor reliability, supply chain bottlenecks, logistics costs, lead times, and delivery performance** within the FedEx logistics dataset.

The analysis identified **shipment mode, fulfillment method, vendor, INCO terms, and country** as important factors associated with logistics cost and delivery performance. It also highlighted the distinction between factors associated with the **occurrence of delays and the extent of delays**, providing a more targeted understanding of delivery performance.

Overall, the findings provide data-driven insights that can support **cost optimization, improved delivery reliability, greater operational efficiency, and better strategic and operational decision-making**.

---

# Project Structure

```text
supply-chain-eda-project/
│
├── EDA_Project.ipynb
└── README.md
```

---

# Project Author

Vimala G

