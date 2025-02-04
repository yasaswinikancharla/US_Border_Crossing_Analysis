# US_Border_Crossing_Analysis

U.S BORDER CROSSING ANALYSIS DASHBOARD
Borders are fundamental to a nation's economic stability, security, and international relations. The United States shares significant borders with Canada and Mexico, which are essential for trade, tourism, and immigration. It is imperative to monitor and assess the crossing patterns at these borders to facilitate the efficient functioning of ports, enhance border management practices, and adapt to new trends or policy developments.
By using a Power BI dashboard, this project will provide an in- depth analysis of border crossing data in United States. I intend to analyze the traffic patterns, performance of the key ports, different crossing types and their impact. Used various data visualization methods and DAX (Data Analysis Expressions) measures. Prepared a dashboard to serve as an effective resource for 	stakeholders, empowering them to make well-informed decisions grounded in data-driven insights. 
Objective:
The primary objective of this project is to build an interactive dashboard analyzing the border crossing activity across U.S- Canada and U.S – Mexico Border which includes:
•	Analyzing the traffic patterns like seasonal fluctuations, traffic growth or decline, any policy changes or global events. 
•	Crossing Type and their distributions across each port and border, different types of crossing and their contribution to the overall traffic. 
•	By using map visualizations, this dashboard will help the stakeholders to comprehend the geographical distribution of border crossing and help identify the borders and ports that experience high traffic. 

Dataset Overview: 
•	Source: Border Crossing Entry Data - Catalog (Collected from www.Data.gov) 
•	Meta Data: 
Port Name	Records the port where the crossing has occurred.
State	The state where the port is located.
Border	The neighboring country from where the crossing is happening. (U.S- Canada and U.S- Mexico).
Date	Records the month and year of the crossing record.
Measure	The mode of transportation used to cross the border. (Eg: Buses, Trucks etc.,)
Latitude and Longitude	Geo-spatial data for port’s location.
Value	The number of crossings happened. 


Tools and Technologies: 
•	Power BI: For creating data visualizations and dashboard creation.
•	Power Query: For cleaning and transformation of data.
•	Microsoft Excel: For the initial exploration of the data.
•	DAX (Data Analysis Expressions): For creating calculated measures and performing advanced analytics.
Data Analysis of U.S. Border data:
•	Data Cleaning and Preparation:
-	Import data into Power BI.
-	Used Power Query to clean and transform the data:
o	Removed rows with null values.
o	Removed the rows with duplicate values.
o	Checked and converted the data types of the columns as needed. 
o	Changed the name of a column named “Measures” to “Crossing Type”.
•	Data Analysis: 
Created a few calculated measures for in-depth analysis of border crossings and provided some actionable insights. 
1.	Total Crossings: 
Formula: Total Crossings = SUM (Border_Crossing_Data’[Value])
Purpose: This measure can be used to measure an overview of traffic volume, benchmarking and as an input for other calculations.
2.	Crossing Trend (3-Month Moving Average):
Formula: Crossing Trend (3-Month Moving Average) = Calculate (AVERAGEX(DATESINPERIOD(Border_Crossing_Data’[Date], LASTDATE(Border_Crossing_Data’[Date]), -3, MONTH), [Total Crossings]))
Purpose: This measure calculates the moving average of border crossing over the past 3 months, which helps us focus on long-term trends ignoring the short-term fluctuations.


3.	Port Crossing Percentage
Formula: Port Crossing Percentage = DIVIDE(SUM('Border_Crossing_Data'[Value]), CALCULATE(SUM('Border_Crossing_Data'[Value]), ALL ('Border_Crossing_Data'[Port Name])) * 100
Purpose: Using this measure, we can see which border crossing ports are the most important in terms of traffic volume. A higher percentage   indicates a critical border crossing point that may require more attention or resources.
4.	Total Passenger: 
Formula: Total Passengers = CALCULATE(SUM('Border_Crossing_Data'[Value]), 'Border_Crossing_Data'[Crossing Type] IN{"Passengers", "Pedestrians", "Buses"})
Purpose: This measure sums up the number of passengers crossing the border, mainly the pedestrians and buses. 
5.	Total Vehicles:
Formula: Total Vehicles = CALCULATE( SUM('Border_Crossing_Data'[Value]), 'Border_Crossing_Data'[Crossing Type] IN{"Personal Vehicles", "Trucks", "Commercial Vehicles"} )
Purpose: This measure sums up the number of vehicles crossing the border, mainly personal vehicles, trucks, and commercial vehicles like trucks. 
6.	Passenger to Vehicle ratio:
Formula: Passenger to Vehicle Ratio = DIVIDE ([Total Passengers], [Total Vehicles])
Purpose: Calculates the ratio between passenger crossings and vehicle crossings, which provides an insight into the balance between these two types of traffic. 

•	Visualization:
-	Tree Map Visualization:
Purpose: This visualization is used to show how the individual high performing ports contribute to the whole. This visualization represents the ports with port crossing percentage greater than equal to 5.2.
 

	The visualization has a tooltip of Port Name, Total Crossings and the Port Crossing Percentage of the selected ports. 
•	Donut Chart:
 
This visualization is used to compare the ratio of Total Passengers to Total Vehicles crossings, representing the visual representation of different types of traffic contributing to the overall border traffic. 
This gives an insight that the traffic is passenger traffic or vehicle traffic, allowing the stakeholders to allocate resources more effectively and also if there is a need for new infrastructure among the ports to handle large volume of traffic. 
•	Geographical Analysis: Map Visualization
Purpose: This visualization provides a geographical overview of border traffic, showing the number of crossings at each port of entry along the U.S.-Canada and U.S.-Mexico border which help the users to understand the spatial distribution of the traffic. 
 









•	Sunburst Diagram: 

Purpose:  This Sunburst diagram shows how different types of border crossings happen at specific borders, like between the U. S-Mexico and between the U. S-Canada. It shows where and how much traffic is in different groups, giving a clear view of how traffic is divided by type of crossing and border.
 

•	Decomposition Tree: 

Purpose: The Decomposition Tree is a useful tool for understanding the different reasons behind the total number of border crossings. It lets users look at the data in an interactive way, exploring different aspects like borders, types of crossings, and states to see what affects traffic levels.
 
•	Line and Clustered Column Chart
Purpose: The Line and Clustered Column Chart shows how trends and actual crossing volumes provide performance of ports over time. This visualization is particularly useful for identifying seasonal patterns and trends at specific ports.
 

•	Time Series Analysis: Area Chart 
Purpose: This area chart shows how border crossings have changed over the years, highlighting the overall trend in traffic. This chart shows a simple and clear picture of border activity over time year by year.
 
•	Insights and Recommendations:
This analysis emphasizes various important findings:
o	There are substantial disproportionate traffic volumes across different ports, especially around U.S-Mexico Border, which indicates the need for increased resource allocation.
o	This dashboard also uncovers differences across different ports and borders with different types of crossings. For instance, there are few ports which serve mainly as passenger entry point, while other ports as commercial vehicle entry points. 
o	The time series analysis also highlights the impact of external factors, such as policy changes, economic conditions, and global events on border traffic volumes. 
•	Recommendations: 
o	Optimizing Resource Allocation Based on Port Performance: Implement a dynamic resource allocation strategy that adjusts based on traffic volume and vehicle type at each port. High-traffic ports, especially those with a substantial share of commercial vehicle crossings, should be prioritized for infrastructure enhancements, increased staffing levels, and improved security protocols. This approach ensures resources are utilized efficiently to meet demand and maintain operational effectiveness.
o	Enhancing Infrastructure for Passenger and Pedestrian Crossings: Focus investments on ports with a high passenger-to-vehicle ratio by improving pedestrian processing infrastructure. Key upgrades should include dedicated pedestrian lanes, sheltered walkways, and enhanced security screening facilities to ensure a smoother and more efficient crossing experience.
o	Preparing for Seasonal Fluctuations: Establish strategies to effectively manage seasonal surges in border crossings. These strategies could include deploying additional temporary staff during peak periods, extending or adjusting operating hours, and leveraging data analytics to forecast and prepare for traffic spikes. This proactive approach ensures efficient operations and minimizes delays during high-demand times.
o	Focusing on High-Impact Ports for Security Enhancements: Direct security improvements to ports with substantial crossing volumes that serve as critical hubs for high-value or sensitive goods. Enhancements may include advanced surveillance systems, enhanced cargo inspection technologies, and increased security personnel to mitigate risks and ensure the safe and efficient movement of goods.
o	Implementing Data-Driven Border Management Policies: Leverage dashboard insights to shape and refine border management policies. For instance, policies affecting trade and travel should incorporate year-over-year growth trends and focus on the crossing types most influenced. This data-driven approach ensures policies are responsive, targeted, and aligned with evolving traffic patterns and stakeholder needs.
Utilizing the dashboard’s features empowers stakeholders to make data-driven decisions that boost operational efficiency, strengthen security, and streamline cross-border travel. Additionally, its interactive design allows for continuous updates and refinements, ensuring it adapts to the ever-changing dynamics of border crossings.
The U.S. Border Crossing Analysis Dashboard is more than just a tool for managing current operations—it is a strategic asset for future planning. By implementing the outlined recommendations, border authorities can enhance management efficiency, proactively address emerging trends, and uphold the security and functionality of U.S. borders in an evolving landscape.

