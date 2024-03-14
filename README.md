  #  Customer Analysis Project

## Table of Contents
---
### [Project Overview](project-overview)
### [Data Source](data-source)
### [Tools](tools)
### [Data Cleaning](data-cleaning)
### [Exploration Data Analysis](exploration-data-analysis)
### [Data Analysis](data-analysis)
### [Results/ Findings](results/findings)
### [Recommendations](recommendations)



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
- Which states have a moderate number of customers in the 'Consumer' segment?
- Which states have the lowest number of customers in the 'Consumer' segment?
- What is the distribution of customers across different states?


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
- **Distribution Across States**: The customer distribution across different states varies significantly, with some states having a larger customer base compared to others.
  
- **Highest Customer States**: The analysis revealed that states such as California, Texas, New York, Ohio, Washington, Illinois, Florida, and Colorado, have the highest number of customers in the 'Consumer' segment.

- **Moderate Customer States**: The analysis revealed that states such as Arizona, Kentucky, Minnesota, Michigan, Indiana, Georgia, Virginia, and Delaware, have a moderate number of customers in the 'Consumer' segment.

- **Low Engagement States**: States like Alabama, Mississippi, Missouri, Louisiana, Oregon, New Mexico, Rhode Island, Nebraska, Lowa, and Arkansas were found to have particularly low customer engagement, indicating potential areas for improvement in marketing strategies or customer outreach initiatives.
  
- **Marketing Focus States**: States such as Florida, Illinois, and Georgia were identified as needing more marketing efforts to increase customer engagement, as they showed lower customer counts compared to other states.

- **Strategic Insights**: Overall, the analysis provided valuable insights into customer distribution patterns across states, highlighting key areas for targeted marketing campaigns and strategic decision-making to optimize business growth.

  
  ![SQL insight](https://github.com/Clifford254KE/SQL/assets/140185917/b1be4b9a-fd90-46a6-8a9b-8908ae0bb47a)!
  
This is the SQL dataset that was used in Tableau for dashboarding


![Customer Analysis Dashboard](https://github.com/Clifford254KE/Customer-Analysis/assets/140185917/f16d1930-2280-44ef-8c07-91cd6e9227bf)

This is the interactive dashboard created using Tableau. You can check it [here](https://public.tableau.com/app/profile/cliffford.otieno/viz/CustomerAnalysisDashboard_17104082861570/CustomerAnalysisDashboard?publish=yes)

### Recommendations
---
- **Targeted Marketing Campaigns**: Focus on states with the highest customer concentration, namely California, Texas, New York, Ohio, Washington, Illinois, Florida, and Colorado. Implement targeted marketing campaigns tailored to the preferences and needs of customers in these states to further solidify market presence and enhance customer loyalty.

- **Strategic Expansion**: Consider expanding operations and marketing efforts in states with moderate customer counts such as Arizona, Kentucky, Minnesota, Michigan, Indiana, Georgia, Virginia, and Delaware. These states represent potential growth opportunities where increased marketing efforts could lead to capturing a larger market share.

- **Enhanced Engagement Strategies**: Devise specialized engagement strategies for states with low customer engagement levels such as Alabama, Mississippi, Missouri, Louisiana, Oregon, New Mexico, Rhode Island, Nebraska, Iowa, and Arkansas. Implement initiatives aimed at enhancing brand awareness, improving customer satisfaction, and fostering stronger relationships with customers in these regions.

- **Marketing Focus Adjustment**: Redirect marketing resources towards states requiring more attention, including Florida, Illinois, and Georgia, which exhibit lower customer counts compared to other states despite their potential. Launch targeted marketing campaigns and promotional activities specifically designed to resonate with the preferences and demographics of customers in these states, aiming to increase customer engagement and drive sales growth.

- **Cross-functional Collaboration**: Foster collaboration between marketing, sales, and customer service teams to ensure alignment of strategies and seamless execution of marketing campaigns across different states. Encourage knowledge sharing and exchange of insights to leverage collective expertise and optimize customer acquisition and retention efforts nationwide.
