# Exploratory Data Analysis (EDA) using SaaS Business Metrics - Project Overview
## This project aims to explore a fictitious B2B SaaS company's dataset. Analysis focuses on discovering patterns, trends, and insights about sales dynamics, customer behavior, and profitability. Key questions involve revenue, profitability, discounting strategies, and product performance. Objective is to offer actionable insights to improve decision-making and business performance.

## Dataset Structure
Dataset that is used in this analysis is the "Amazon SaaS Sales Data Analysis" data available on Kaggle (https://www.kaggle.com/datasets/nnthanh101/aws-saas-sales/code).
It is structured as follows:

- **Row ID**: Unique ID per data row (removed during preprocessing)
- **Order ID**: Unique ID for each order
- **Order Date**: The date the order was placed
- **Date Key**: Order date key (in yyyymmdd format)
- **Contact Name**: Name of the individual representative from the ordering company (removed during preprocessing)
- **Country**: The country where the ordering company conducts business
- **City**: The city where the ordering company conducts business
- **Region**: The continent (business region) of the company's business activities
- **Subregion**: The subregion of the area where the company's business activities occur
- **Customer**: Name of the ordering company
- **Customer ID**: Unique ID for the ordering company
- **Industry**: Economic domain/activity of the ordering company
- **Segment**: Type/category of the ordering company
- **Product**: Name/type of the product
- **License**: Unique usage license for one product type per order (removed during preprocessing)
- **Sales**: Total sales value of one product type per order
- **Quantity**: Number of units sold for one product type per order
- **Discount**: Percentage discount for one product type per order
- **Profit**: Total profit from sales of one product type per order (renamed to `net_profit` during preprocessing)

Additional columns created during preprocessing:
- **total_discount_in_dollars**: Total discount given in dollars
- **selling_price**: Sales value of one unit of the product
- **(net)_profit_before_discount**: Net profit before the application of the discount
- **net_profit_per_unit_sold**: Net profit for the sale of one unit of the product
- **profit_margin**: Profit margin as a percentage
- **discounted_sales**: Sales value after applying the discount
- **overall_cost**: Overall cost per order
- **year**: Year extracted from the `Order Date`
- **year_month**: Year and month extracted from the `Order Date`
- **month**: Month extracted from the `Order Date`

## Insights Summary

#### Revenue
- **Higher revenue** in March, September, November, and December, with peaks in November ($74,081) and December ($72,616).
- **Revenue declines** in February 2023 ($16,855) vs. February 2022 ($21,603) and December 2023 ($78,650) vs. December 2022 ($87,898).
- **Highest YoY growth** in 2022 at 29.4%, slightly lower in 2023 at 19.87%.
- **Annual revenue** between $406,690 (2020) and $632,548 (2023) places the company in the early-stage bracket, aiming for top-line growth and market share.

#### Profitability
- **Highest monthly profit** in October 2022 ($15,763) and December 2022 ($17,903).
- **More stable profit** in 2023 with strong performance in March ($12,958), September ($11,395), and August ($8,894).
- **Varied growth rates**: 2021 revenue up 0.24%, net profit up 24.37%; 2022 revenue up 29.44%, net profit up 32.63%; 2023 revenue up 19.87%, net profit up 14.41%.
- **Improvement needed** to balance revenue and net profit, with 2022 surpassing the Rule of 40.

#### Discounting
- **Positive correlation** between "Discounts YoY" and "Sales YoY," but diminishing returns on profitability.
- **Stable discounting strategies** for higher margin products like SaaS Connector Pack - Gold and Support.
- **Aggressive discounts** for lower margin products like ContactMatcher and OneView, leading to instability.
- In 2023, some products maintained profitability, while others had **Average Overall Sales Costs** exceeding **Average Sales**, limiting discount options.

#### Product Performance

| Product                    | Avg. Active Users | Revenue     | Revenue Growth & Trajectory | Net Profit  | Profit Margin & Trajectory | Discounting                         | Product Challenges                                    |
|----------------------------|-------------------|-------------|-----------------------------|-------------|----------------------------|-------------------------------------|-------------------------------------------------------|
| Alchemy                    | Low               | Moderate    | High, Declining             | High        | High, Increasing           | Cost efficient (20%, 40% Discounts) | User-Centric Improvements                             |
| Big Ol Database            | Low               | Moderate    | Low, Declining              | Negative    | Negative, Declining        | Discount threshold (31% Discount)  | Cost Reduction, Product Improvement                   |
| ChatBot Plugin             | Moderate          | Low         | Low, Increasing             | Low         | Moderate, Stable           | Cost efficient (20% Discounts)      | Feature Development, Tiered Packages                    |
| ContactMatcher             | High              | High        | Low, Stable                 | Negative    | Low, Declining to Negative | Discount threshold (24% Discount)  | Strategic Adjustment, Product Improvement, Tiered Packages             |
| Data Smasher               | Moderate          | Moderate    | Moderate, Stable            | High        | High, Stable               | Cost efficient (20% Discounts)      | Maintain Performance and User Experience              |
| FinanceHub                 | Moderate          | High        | Low, Increasing             | Moderate    | Low, Stable                | Discount threshold (22% Discount)  | Maintain Pricing, Product Improvement                 |
| Marketing Suite            | Low               | Low         | Low, Stable                 | Negative    | Negative, Stable           | Discount threshold (19% Discount)  | Relevancy                                             |
| Marketing Suite - Gold     | Moderate          | Moderate    | Low, Increasing             | Moderate    | High, Stable               | Discount threshold (17% Discount)  | Expand Market Reach, Product Improvement, Tiered Package              |
| OneView                    | Moderate          | Moderate    | Moderate, Stabilizing       | Moderate    | Low, Increasing             | Discount threshold (33% Discount)  | Product Improvement, Operational Efficiency           |
| SaaS Connector Pack        | Moderate          | Low         | Moderate, Decreasing        | Low         | Low, Stable                | Discount threshold (26% Discount)  | Partnerships and Integrations, Product Improvement    |
| SaaS Connector Pack - Gold | Low               | Low         | Low, Decreasing             | Low         | High, Stable               | Cost efficient (20% Discounts)      | Conversion to Standard Version                        |
| Site Analytics             | Moderate          | High        | Low, Increasing             | High    | Low, Stable           | Discount threshold (26% Discount)  | Maintain Pricing, Product Improvement |
| Storage                    | Low               | Low         | Low, Declining              | Low         | Moderate, Increasing       | Cost efficient (20% Discounts)      | Maintain cost-efficiency                                        |
| Support                    | High              | Moderate    | Moderate, Increasing        | Moderate    | Moderate, Stable           | Cost efficient (20% Discounts)      | Maintaining Profit and Value Delivery                 |


## Recommendations

- **Cost Management**:
  Big Ol Database, Marketing Suite, and ContactMatcher all struggle with high costs impacting their profits. Their performance in 2023 shows that losses have exceeded profitable periods. Big Ol Database's profitability is declining, and Marketing Suite is unable to cover its costs. Despite high revenue, ContactMatcher experienced a negative profit margin due to rising costs. Reducing costs, especially for ContactMatcher, given its strong market demand and revenue potential, is essential to boosting overall profitability and ensuring sustainable growth.

- **Leverage Cost-Efficient Products**:
  Focus on promoting and expanding the six cost-efficient products that have demonstrated good profitability and stable discounting strategies: Support, Data Smasher, ChatBot Plugin, Storage, SaaS Connector Pack - Gold, and Alchemy.

  Among these, three products have shown the highest profitability and stable margins, making them key targets for expansion to maximize profitability and ensure sustainable growth:
  - Alchemy: Focus on user-centric improvements to attract and retain users, stabilize revenue, and grow profit margins through long-term engagement.
  - Data Smasher: Maintain performance and continuously enhance user experience.
  - Support: Leverage its loyal user base to maintain and grow its market position.

- **Maintain Performance of "Cash-cow" Products**:
  "Cash-cow" products are those that consistently generate high revenue and profit margins with minimal investment. These products typically enjoy strong market presence and customer loyalty, leading to steady demand and sales. Being in the mature stage of their product life cycle, they require minimal marketing or development expenses to sustain profitability. As a reliable source of income, cash-cow products fund other experimental or growth-oriented ventures within a company.
  - Site Analytics & FinanceHub: Revenue growth has slowed, but a stable profit margin shows that customers see ongoing value. To capitalize on this, maintain pricing and enhance features.

- **Reassess Discount Strategies**:
  Evaluate the long-term sustainability of aggressive discounting practices to ensure they drive sales without significantly harming profit margins. However, especially for eight products that had their Average Overall Sales Cost exceed the Average Sales generated, the effectiveness of further discounting is limited. These products must have their discounting thresholds set below the following optimal percentages based on the data:
  - FinanceHub: 22%
  - Site Analytics: 26%
  - Marketing Suite - Gold: 17%
  - ContactMatcher: 24%
  - SaaS Connector Pack: 26%
  - OneView: 33%
  - Marketing Suite: 19%
  - Big Ol Database: 31%

- **Dataset Limitation**:
  Lack of detailed cost data in the dataset makes it challenging to accurately assess profit and profitability. While net profit provides a comprehensive view, it combines all expenses, which can distort real-world insights and hinder decisions related to cost management, such as customer acquisition cost (CAC) and discount optimization. To address this, it is essential to collect and integrate detailed cost data, including the cost of goods sold (COGS) and customer acquisition costs (CAC). This would enable the calculation of key metrics like the LTV:CAC ratio, which is vital for evaluating the efficiency of customer acquisition efforts in SaaS. Alternatively, gathering both gross profit and net profit data allows for a more precise analysis of profitability by separating production costs from other operational expenses. This dual approach enhances cost management and strategic decision-making.

- **Strategic Pricing and Discount Alternatives for SaaS**:
  Discounting can lower perceived value of products, attract price-sensitive customers, and create expectations for more deals, impacting profitability. Research shows (see Reference in report) that initial purchase discounts can reduce perceived value by at least 12%, while free trials and promotions have a lesser effect. In real-world SaaS businesses, discounts are typically bundled with package options and are not extensively used to boost sales. Instead of discounting, consider creating entry-level tiers, adding value through extra features or services, and improving marketing segmentation to better target customer groups.

## Dashboard
An executive dashboard can be found in Tableau Public [here](https://public.tableau.com/app/profile/rizky.sadali/viz/ExecutiveDashboard_17368070287990/ExecutiveDashboard). This dashboard enables company decision-makers to filter by Product, Region, Segment, Periods (Annual, Quarterly, Monthly) and allows decision-makers to drill down into specific areas of interest and cross-checking of the report.

<img width="812" alt="Executive Dashboard" src="https://github.com/Rizky-Sadali/Exploratory-Data-Analysis-EDA-using-SaaS-Business-Metrics/blob/main/Executive Dashboard.png">

## Presentation Sample
A PowerPoint presentation for company executives, detailing the insights and recommendations, is available [here](https://docs.google.com/presentation/d/17HuFP4TC6P0qGJjkaNA-rxmXhKul9UkR/edit#slide=id.p4). For convenience, some extracts are presented below.

<img width="812" alt="sample slide 1" src="https://github.com/Rizky-Sadali/Exploratory-Data-Analysis-EDA-using-SaaS-Business-Metrics/blob/main/sample slide 1.png">
<img width="812" alt="sample slide 2" src="https://github.com/Rizky-Sadali/Exploratory-Data-Analysis-EDA-using-SaaS-Business-Metrics/blob/main/sample slide 2.png">
<img width="812" alt="sample slide 3" src="https://github.com/Rizky-Sadali/Exploratory-Data-Analysis-EDA-using-SaaS-Business-Metrics/blob/main/sample slide 3.png">