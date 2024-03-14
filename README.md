#  Customer Analysis Project

### Project Overview
---
This project involves analyzing customer data to identify states with higher, moderate, and lower customer engagement or sales. Utilizing SQL queries, the analysis categorizes states based on customer counts into three segments: 'better (higher)', 'need_more_marketing (moderate)', and 'bad (lower)'. The insights gained from this analysis inform targeted marketing strategies and resource allocation for business growth.

### Data Source
---

The dataset used in this project contains information about customers, including their state of residence and segment. It includes fields such as:

- State: The state where the customer resides.
- Segment: The segment to which the customer belongs ( 'Consumer', 'Corporate', 'Home Office').

### Tools 
---
- PostgreSQL- Used for storing and querying the customer dataset 
- pgAdmin- A software environment used for writing, testing, and executing SQL queries. 
- Excel for data cleaning
- Tableau for creating a dashboard and reporting

### Data Cleaning and Preparation
---
**Excel**

- Removed duplicates and handled missing values.
- Standardized formats and corrected errors.
- Export cleaned dataset.
  
**PostgreSQL**

- The dataset from Excel was imported in the form of a CSV.
- A query was run to check if there are any available duplicates and missing that might have been missed by Excel.
- A query was then run to meet the objective of the project.
-  The prepared data was then exported to the tableau.
  
**Tableau**

- The prepared dataset was connected to Tableau.
- It was then Explored
- Designed visualizations.
- Shared insights through an interactive dashboard.

### Exploratory Data Analysis (EDA)
---
- Which states have the highest number of customers in the 'Consumer' segment?
- What is the distribution of customers across different states?
- Which states need more marketing efforts to increase customer engagement?
- Are there any states where customer engagement is particularly low, indicating potential areas for improvement?

### Data Analysis
---
This is the code that produced the desired dataset which was used in Tableau for visualization and dashboarding. The code is returning three fields (columns) namely: state, number of customers per state, and ranking per state depending on the available customers. The dataset in uploaded above.
```slq
SELECT state, COUNT (segment) AS number_of_customers_per_state, 
(CASE WHEN COUNT (segment)> 10 THEN 'better'
     WHEN COUNT (segment)> 5 THEN 'need_more_marketing'
	 ELSE 'bad' END) AS ranking_of_states
FROM customer
WHERE segment = 'Consumer'
GROUP BY state
ORDER BY number_of_customers_per_state DESC;
```
### Results/Findings
---
- **Highest Customer States**: The analysis revealed that states such as California, Texas, and New York have the highest number of customers in the 'Consumer' segment.

- **Distribution Across States**: The customer distribution across different states varies significantly, with some states having a larger customer base compared to others.

- **Marketing Focus States**: States such as Florida, Illinois, and Georgia were identified as needing more marketing efforts to increase customer engagement, as they showed lower customer counts compared to other states.

- **Low Engagement States**: States like Wyoming, Vermont, and Montana were found to have particularly low customer engagement, indicating potential areas for improvement in marketing strategies or customer outreach initiatives.

- **Strategic Insights**: Overall, the analysis provided valuable insights into customer distribution patterns across states, highlighting key areas for targeted marketing campaigns and strategic decision-making to optimize business growth.

  
  ![SQL insight](https://github.com/Clifford254KE/SQL/assets/140185917/b1be4b9a-fd90-46a6-8a9b-8908ae0bb47a)![Tableau Viz](https://github.com/Clifford254KE/SQL/assets/140185917/9a44ed7d-b1d1-45cb-97a0-012fc4de570b)



### Recommendations
---
- **Targeted Marketing Campaigns**: Focus marketing efforts on states with the highest number of customers, such as California, Texas, and New York, to maximize customer engagement and retention.

- **Regionalized Marketing Strategies**: Develop region-specific marketing strategies tailored to states needing more marketing efforts, such as Florida, Illinois, and Georgia, to effectively target and attract customers in these areas.

- **Improved Outreach Initiatives**: Implement targeted outreach initiatives in states with low customer engagement, such as Wyoming, Vermont, and Montana, to increase brand awareness and drive customer acquisition.

- **Data-Driven Decision Making**: Continuously monitor and analyze customer distribution patterns to identify emerging trends and adjust marketing strategies accordingly, ensuring a proactive and data-driven approach to decision-making.

- **Customer Segmentation Refinement**: Further refine customer segmentation strategies based on geographical location and other relevant factors to better understand regional preferences and behavior, enabling personalized marketing approaches for enhanced customer satisfaction and loyalty.
