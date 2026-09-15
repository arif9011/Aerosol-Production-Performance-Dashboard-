# Aerosol-Production-Performance-Dashboard-
•	Created a Power BI-ready fictional manufacturing dataset containing 180 production records. 
•	Designed KPIs for output attainment, reject rate, downtime, availability, performance, quality and OEE. 
•	Analyzed production performance by date, shift, line and downtime reason. 
•	Created an interactive dashboard design using Excel, Power Query concepts and DAX measures. 
•	Used fictional information to maintain employer and customer confidentiality.



Aerosol production performance dashboard														
														
Fictional 60-day dataset for Power BI practice														
														
Good Units				Output Attainment				Reject Rate				OEE		
3,599,267				86.6%				2.1%				79.8%		
														
Measure	DAX formula	Format	
Planned Units	Planned Units = SUM(AerosolProduction[Planned Units])	Whole number	
Total Units	Total Units = SUM(AerosolProduction[Total Units])	Whole number	
Good Units	Good Units = SUM(AerosolProduction[Good Units])	Whole number	
Rejected Units	Rejected Units = SUM(AerosolProduction[Rejected Units])	Whole number	
Downtime Minutes	Downtime Minutes = SUM(AerosolProduction[Downtime Minutes])	Whole number	
Run Minutes	Run Minutes = SUM(AerosolProduction[Run Minutes])	Whole number	
Availability	Availability = DIVIDE([Run Minutes], SUM(AerosolProduction[Planned Minutes]))	Percentage, 1 decimal	
Theoretical Run Minutes	Theoretical Run Minutes = SUMX(AerosolProduction, AerosolProduction[Total Units] * AerosolProduction[Ideal Cycle Seconds] / 60)	Decimal, 1 place

Performance	Performance = DIVIDE([Theoretical Run Minutes], [Run Minutes])	Percentage, 1 decimal	
Quality	Quality = DIVIDE([Good Units], [Total Units])	Percentage, 1 decimal	
OEE	OEE = [Availability] * [Performance] * [Quality]	Percentage, 1 decimal	
Reject Rate	Reject Rate = DIVIDE([Rejected Units], [Total Units])	Percentage, 1 decimal	
Output Attainment	Output Attainment = DIVIDE([Good Units], [Planned Units])	Percentage, 1 decimal	
			
			
Date-table item	DAX formula	Use	
Date Table	Date Table = CALENDAR(MIN(AerosolProduction[Date]), MAX(AerosolProduction[Date]))	Create as New table	
Month	Month = FORMAT('Date Table'[Date], "MMM yyyy")	Create as calculated column	
Month Sort	Month Sort = YEAR('Date Table'[Date]) * 100 + MONTH('Date Table'[Date])	Sort Month by this column	
			
<img width="1211" height="531" alt="image" src="https://github.com/user-attachments/assets/7c483868-c1aa-4ea5-9713-4cd456141dd4" />
													
												
														
Use the Power BI Guide sheet to recreate this layout interactively. All data is fictional and designed only for learning and portfolio practice.														
														
<img width="1691" height="1059" alt="image" src="https://github.com/user-attachments/assets/01cdaf90-5e45-495d-9663-e082bd0e8986" />
