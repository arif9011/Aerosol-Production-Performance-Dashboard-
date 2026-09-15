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

Good Units = SUM(AerosolProduction[Good Units])
Rejected Units = SUM(AerosolProduction[Rejected Units])
Downtime Minutes = SUM(AerosolProduction[Downtime Minutes])
Run Minutes = SUM(AerosolProduction[Run Minutes])
Availability = DIVIDE([Run Minutes], SUM(AerosolProduction[Planned Minutes]))
Theoretical Run Minutes = SUMX(AerosolProduction, AerosolProduction[Total Units] * AerosolProduction[Ideal Cycle Seconds] / 60)
Performance = DIVIDE([Theoretical Run Minutes], [Run Minutes])
Quality = DIVIDE([Good Units], [Total Units])
OEE = [Availability] * [Performance] * [Quality]
Reject Rate = DIVIDE([Rejected Units], [Total Units])
Output Attainment = DIVIDE([Good Units], [Planned Units])

DAX Formula 

Date Table = CALENDAR(MIN(AerosolProduction[Date]), MAX(AerosolProduction[Date]))
Month = FORMAT('Date Table'[Date], "MMM yyyy")
Month Sort = YEAR('Date Table'[Date]) * 100 + MONTH('Date Table'[Date])

<img width="781" height="76" alt="image" src="https://github.com/user-attachments/assets/5340614a-9ffb-4b15-abf8-1c9058f1e823" />

<img width="781" height="291" alt="image" src="https://github.com/user-attachments/assets/71b1f937-2673-4e80-b346-cc191541a3c9" />

			
<img width="1211" height="531" alt="image" src="https://github.com/user-attachments/assets/7c483868-c1aa-4ea5-9713-4cd456141dd4" />
													
												
														
Use the Power BI Guide sheet to recreate this layout interactively. All data is fictional and designed only for learning and portfolio practice.														
														
<img width="1691" height="1059" alt="image" src="https://github.com/user-attachments/assets/01cdaf90-5e45-495d-9663-e082bd0e8986" />
