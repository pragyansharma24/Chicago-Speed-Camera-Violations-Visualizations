# Chicago Speed Camera Violations
## Background
Chicago experiences a high number of crashes between vehicles and pedestrians, about 25% of which involve children. Automated Speed Camera Program is a part of Children’s Safety Zone Program. According to the City of Chicago [[Ref 1]](https://www.chicago.gov/city/en/depts/cdot/provdrs/automated_enforcement/news/2018/july/automated-speed-enforcement-cameras-to-be-activated-in-response-.html), “the Children’s Safety Zone Program protects children and other pedestrians by reminding motorists to slow down and obey speed laws – especially in school and park zones.” Safety zones are designated as a 660-foot boundary around any parks or schools. Per the City of Chicago [[Ref 1]](https://www.chicago.gov/city/en/depts/cdot/provdrs/automated_enforcement/news/2018/july/automated-speed-enforcement-cameras-to-be-activated-in-response-.html), “revenue collected from the program will be utilized for programs that enhance the safety of children, including afterschool, anti-violence and jobs programs; crossing guards and police officers around schools; and infrastructure improvements, such as signs, crosswalk markings and other traffic safety improvements.”

## Data Sources
**Speed Camera Violations:** Contains speed violations recored by automated speed cameras installed by the City at Safety Zones. Data used in the present analysis is obtained from the City of Chicago Data Portal [[link]](https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/hhkd-xvj4). </br>
**Safety Zone Data:** Contains name and address of a school or park near which a camera is installed. Safety Zone is defined as the area within the 1/8th mile radius of a school or park. Data used in the present analysis is obtained from the link [[here]](https://www.chicago.gov/content/dam/city/depts/cdot/Red%20Light%20Cameras/2017_Automated_Enforcement_Report20180427.pdf). </br>
**Vehicle Crash Data:** Contains crash statistics (e.g. fatal crashes, pedestrian bicycle crashes, etc.) for city-wide locations and for the locations in Safety Zones where speed cameras are installed. Crash data are available for years 2012-2013, years before Safety Zone cameras were installed, and for 2015-2016, years after Safety Zone camera were installed. Data used in the present analysis are obtained from the link [[here]](https://www.chicago.gov/content/dam/city/depts/cdot/CSZ/ASE_CrashAnalysisWriteUp_10_10_18.pdf). 

## Data Description  

A brief description of the variables used in the present analysis is as follows:</br>
**Operational Camera Day:** Each record (or row) in Speed Camera Violations data is for a certain day when a camera is operational.   It is possible that a camera is not opertational on some days, e.g. school cameras are not operational on weekends. </br>
**Violations:** Each record (or row) in the Speed Camera Violations dataset has the number of violations captured by a camera on a particular Operational Camera Day. A camera on a given Operational Camera Day may have multiple violations.</br>
**Violation Date:** Date corresponding to an Operational Camera Day for which violations are provided. Note that exact time of violation is not provided in the data. </br>
**Camera Location:** Camera location is the location where camera is located; it is specified in terms of Latitude/Longitudes or in State Plane Coordinate System. </br>
**Safety Zone:** Safety zone is defined as the area in the 1/8th mile radius of a school or park. There are only two possible types of Safety Zones: School Zone and Park Zone. </br>
**Address:** Address of the location of the speed enforcement camera(s). There may be more than one camera at each address. It is confirmed that the Latitude-Longitude coordinates are identical to X-Y coordinates in State Plane System.  </br>
**Camera ID:** A unique ID associated with the physical camera at each location. There may be more than one camera at a physical address.

## Trendline for Total Violations
**Analysis and Insights:**
To understand the trend of total violations in the Safety Zones around Chicago, the Speed Camera Violations data mentioned above was used. Figure 1 below shows that since the installation of automated speed cameras in Safety Zones, total speed violations recorded by all cameras are on the decline. Based on the results in Figure 1, it is observed that the total violations are decreasing at an average rate of 4.43 violations per day. Based on the information available from sources, this decline can be attributed to two major factors: 
1. Drivers are now more aware of the camera locations and associated violation rules. This is also in accordance with the findings documented in the annual report published by the City of Chicago [[Ref 2]](https://www.chicago.gov/content/dam/city/depts/cdot/Red%20Light%20Cameras/2017_Automated_Enforcement_Report20180427.pdf). It says, “In 2017, 90 percent of drivers that were issued a ticket for speeding in a school zone and 73 percent of drivers that were issued a ticket for speeding in a park zone did not receive a second ticket during the year, indicating they changed their behavior.” 
2. Policies related to speed camera violations have been changed over the years by the government after people complained about tickets they received, claiming violations were not legal. For example, per [[Ref 3]](https://www.illinoispolicy.org/390000-drivers-set-to-receive-refunds-for-red-light-and-speed-camera-tickets/), around 390,000 drivers were set to receive refunds as a result of a lawsuit. Further, removal of cameras at some locations, and change in policies regarding violation tickets to make the program more efficient may also have contributed to the declining number of violations. 

<p align="center">
<img src="Declining_Speed_Violations.JPG" alt="Trend of Violations" width="800">
</p>
<p align="center">
  <b>Figure 1: Trend of Total Weekly Violations</b>
<p>

With regards to revenue generated by the Speed Camera Violations program, Figure 1 also provides insights for the Mayor and his team. Per Chicago Tribune [[Ref 4]](http://apps.chicagotribune.com/news/local/chicago-speed-camera-tickets/cameras/4909-n-cicero-ave/), “the 146 cameras placed around 61 parks and schools have generated more than $81 million in tickets through Sept. 1, 2015.” Although more recent data on revenue earned could not be found, but it is obvious that the revenue earned through the Speed Camera Program is a significant source of income that the City has planned to use for the causes mentioned above [[Ref 1]](https://www.chicago.gov/city/en/depts/cdot/provdrs/automated_enforcement/news/2018/july/automated-speed-enforcement-cameras-to-be-activated-in-response-.html). With increased awareness among people and with improved efficiency in the system since the program started, the revenue amount is supposed to decrease in future, and the City should design its future policies regarding children’s safety program taking this revenue decline into account. 

**Basis for Chart Selection**
* Final vesrion of the chart is shown in Figure 1. 
* Line charts are often the preferred chart type for showing trends in the data, and blue color is the standard chart color. During the data-exploration phase of this project, red-blue colormap for this chart was used; however, it is now realized that colors are actually not required and may distract the reader. Single color is eventually utilized for the final version. 
* Weekly chart for the violations data gives a clearer picture without losing granularity of the data. Although similar trend can be observed in annual, monthly or daily charts but weekly chart appears to be more readable, less distracting, and less cluttered. Daily chart is found noisy and contains more information than actually needed to convey the message of declining violation trend.   
* Labeling a few high and low points increases readabilty and relatabilty. 
*  It is observed that adding operations like running mean, cummulative sum, etc. to the data doesn't really add any useful insights so are not applied to the data. 
* Keeping the audience in mind, the confidence interval lines in the first version of this chart are now removed. 
* Sum of violations was preferred over average violations because it is better associated with the total revenue generated.  

## School Zone Violations in Summer Months
**Analysis and Insights:**
Online article [[Ref 5]](https://www.chicagotribune.com/news/watchdog/ct-speed-camera-bad-tickets-met-20151117-story.html) titled “Emanuel's Speed Cameras Issue $2.4 Million in Bad Tickets” describes loopholes in Chicago’s Speed Camera Program. In this article, author describes instances when tickets given to violators were not legal per City’s own rules. For the present analysis, all data  needed to analyze these instances (e.g. exact time when ticket was issued, park or school operating hours) are not available, but it is possible to analyze one of them, which is the violations that took place near School Zones in summer months of June-August. Per the article, “More than 62,000 school zone tickets were issued over the summer months when school activity is often so limited that drivers are left to guess whether the school is in session or not. The law says tickets can be issued only on school days, typically defined as during the regular school year.”

Per speed camera guidelines provided in [[Ref 1]](https://www.chicago.gov/city/en/depts/cdot/provdrs/automated_enforcement/news/2018/july/automated-speed-enforcement-cameras-to-be-activated-in-response-.html) and the violations data, first, it is confirmed that the speed cameras are installed either in Park Zones or in School Zones, identified by the City of Chicago. To identify if a particular camera belongs to a School Zone or Park Zone, "Safety Zone Data" described above is used (The raw data is in PDF format and was converted to CSV data.) The data provides for each camera ID the nearby school or park name along with its address. The “name” strings that contain the word “Park” were tagged as Park Zone cameras and the rest were tagged as School Zone cameras. A “Park-School” column was then added to the original violations data based on the camera ID. Table 1 below shows number of cameras, total number of days when cameras were active and the total number of violations reported for both Park and School Zones. Violations reported by Park Zone cameras is approximately 4 times higher than by School Zone cameras. Operational Camera Days are also much higher for Park Zone cameras.    

**Table 1: Statistics for Park and School Zone Cameras** </br>

**Zone Type**| **Cameras**| **Operational Camera days** | **Violations**
-------------------- | :----------:  | :----------:  | :----------: 
Park |84 | 130,283 | 4,217,248
School|78 | 54,527 | 1,021,624

Initial data exploration shows that Park Zone cameras are operating on all seven days of a week, whereas School Zone cameras operate only on weekdays (Monday-Friday). No violations on Saturdays and Sundays were recorded by School Zone cameras. This information is also validated using the speed camera guidelines provided in [[Ref 1]](https://www.chicago.gov/city/en/depts/cdot/provdrs/automated_enforcement/news/2018/july/automated-speed-enforcement-cameras-to-be-activated-in-response-.html). Moreover, apart from weekends, it is also found from data exploration that School Zone cameras do not operte on public holidays (e.g. July 4, December 25, January 1, etc.). Figure 2 below shows box-plot diagrams for average speed violations in Park and School Zones. Outlier days recording relatively high number of violations can be clearly seen on box-plot diagrams. Park Zones camera record significantly high number of violations on public holidays (e.g. July 4, December 25, January 1, etc.) but School Zone cameras do not operate on these holidays. It is also observed that School Zone cameras have high violations recorded on Labor Day (September 2 or 3) which is probably an anomaly in the Speed Camera System because, per government regulations, School Zone cameras should not be operational on holidays. 

<p align="center">
<img src="ViolationsonHolidays.JPG" alt="ViolationsonHolidays" width="800">
</p>
<p align="center">
  <b>Figure 2: Average Violations (per camera per day) in School and Park zones</b>
<p>

For previous data exploration assignment, Figure 3 below was used to show a comparison between the "Operational Camera Days" and "Number of Total Violations" for both zones combined. Number of Operational Camera Days provides a measure of when cameras were active or used as traps by the City. For example, as shown in Figure 3 for the month of August, the City puts less number of camera traps in comparison to that in other months.  

<p align="center">
<img src="ComparisionRecordsvsViolations.JPG" alt="ComparisionRecordsvsViolations" width="800">
</p>
<p align="center">
  <b>Figure 3: Total Violations and Operational Camera Days by Year</b>
<p>

This finding gave an idea that it is probably due to the School Zone policy of the City that cameras there did not record violations or were not operational when schools were closed. In general, schools have summer break during the period Mid June - End of August. Therefore, for further analysis, data was partitioned into two categories, Parks and Schools. Figure 4 clearly confirms that the low number of Operational Camera Days in the month of August for schools is a reflection of City's regulations regarding School Zone cameras. In Park Zone cameras, however, this features is not observed. More importantly, for school zone cameras, it can be noticed that significatly higher number of cameras were operational in July than in August. This was likely an error in the system because one would expect same number of operational cameras in both August and July (summer months) in school zones. This error was probably the reason for illegal tickets distributed to the violators in the summer months in school zones as discussed above. 


<p align="center">
<img src="Violations_vs_Camera_Days.JPG" alt="Violations_vs_Camera_Days" width="800">
</p>
<p align="center">
  <b>Figure 4: Total Violations and Operational Camera Days by Safety Zone</b>
<p>

With the visual in Figure 4, we want to send a message to Mayor Rahm Emanuel that action should be taken to correct this illegal ticket distribution during summer months. This will also help in decreasing the burden on ticket processing centers and on the courts hearing the ticket appeals. Drivers in School Zones are also confused whether the cameras are operating or not and as a results average number of tickets in the month of July in School Zones are significantly high. People tend to assume that school cameras are not operating when schools are off. 

**Basis for Chart Selection**
* Final visualization for the analysis is shown in Figure 4.
* The color in the final-version is changed from Brown to Blue. This is done to make color scheme consistent for all visuals. In the final-version, blue color is used everywhere to show violations. 
* Dual-axis chart is preferred in this case. It helps in clearly showing the monthly variation of both Total Violations and Operational Camera Days using one simple plot. Left axis shows Total Violations and the right axis shows the number of days all cameras were operational (or Operational Camera Days). To avoid clutter, bar-type chart is used for only one variable and line chart was used for the second variable.  
* Figure shows both School and Park Zone data. Zones are stacked horizontally for direct and easy comparison.
* Colors for violations for both Park and School Zones are kept same (Blue) for consistency. Choosing different colors does not really provide any benefit. It actually increases clutter due to extra legend item.
* An interactive filter for  Zone Type is added so that the end-user can either look at one Zone Type (School or Park) or all Zone Types at a time.  
* The variable name "Number of Records" is changed to "Operational Camera Days" for more clarity. "Operational Camera days" is clearly defined in the "Data Description" section above.   

## Safety Impact Analysis – Before and After Crashes
**Analysis and Insights:**
The City of Chicago conducted “Safety Impact Analysis of Speed Cameras Program” in 2018 to estimate the efficacy of the speed cameras. Per report generated by the City of Chicago [[Ref 6]](https://www.chicago.gov/content/dam/city/depts/cdot/CSZ/ASE_CrashAnalysisWriteUp_10_10_18.pdf), two major findings of the analysis are as follows:
* Fatal or serious injury crashes decreased 9% near speed cameras, compared to 6% increase city-wide.
* Overall crashes have increased 1% in the automated speed enforcement locations compared to a 21% increase in crashes citywide from 2012-13 to 2015-16 period. "Fatal Crashes" and "Bicycle Pedestrian" crashes have decreased by 9% and 15% respectively. 

These findings create a positive sentiment regarding the speed camera program that it has worked and is contributing towards reducing the number of crashes near the speed camera locations. However, it is noticed that these findings were based on crash incidents reported at all speed camera locations, and they may not provide a true picture for the cameras that are reporting significantly high number of violations. To analyze this, 2-year crash data (2015-2016) was downloaded from the [Ref 6]. Crash data includes, for each Camera ID and for all camera location, number of crashes divided in categories “Total Crashes”, “Serious Fatal”, “Bicycle Pedestrian”, “Speed Related”, and “Youth Related”. Data was processes in Python, and the Python [[Script]](Crash_Violation_Data_Merge_Code.ipynb) is attached with the GitHub project. 

Since the City of Chicago has reported significant improvements in “Serious Fatal” and “Bicycle Pedestrian” type instances, we have focused on these two categories for the present analysis. Figure 5 below shows the change in the number of “Serious Fatal” and “Bicycle Pedestrian” type crashes for speed camera locations sorted by total number of violations. Results show a mixed picture. There may be an overall decrease in crashes for both catagories, but some of these locations with high violations are not showing any improvement in terms of reduction in crashes. Therefore, it is important for the City of Chicago to further investigate the camera locations that are recording a significantly high number of violations but cameras there are not solving the actual purpose for which they have been installed. With the interactive filter on chart, end user can select Top N locations by violations and look at the change in crash statistics.  

<p align="center">
<img src="Impact_of_Camera_Enforcement.JPG" alt="Impact_of_Camera_Enforcement" width="800">
</p>
<p align="center">
  <b>Figure 5: Safety Impact Analysis using Crash Data</b>
<p>
  
**Basis for Chart Selection**
* Final visualization for the analysis is shown in Figure 5.
* The color used for violations in the final version is changed from Grey to Blue. This is done to make color scheme consistent for all visuals. In the final version, Blue color is used everywhere to show violations. 
* After experimenting with different chart types, “bar” charts were used as they provide a clear picture in this case without creating distractions. Use of line plots, in this case, would create difficulty in apprehending the type of data used here.
* First version showed only Top 20 violations cameras. An interactive filter is now added which provides end user an option to select top N cameras.
* Standard Green and Red colors are used to show the reduction and increase in crashes. Reduction in accidents is a positive thing for the Speed Camera Program so it is shown in Green.   
* Percentage change in crashes is used instead of change in crashes. Percentage numbers, in general, provide a better picture due to normalization.
* Figure caption is modified so that it is precise.
* Removed summary from the first version; it does not provide useful information. 
* Colorbar is removed from the first version and proper legends are now used.

## Dashboards
Dashboard with final visualizations:
<p align="center">
<img src="Final_dashboard.jpg" alt="Final_dashboard" width="800">
</p>
<p align="center">
  <b>Figure 6: Final Dashboard</b>
<p>
Tableau Link: https://public.tableau.com/profile/pragyan.sharma#!/vizhome/City_of_Chicago_Speed_Enforcement_Camera_Analysis/FinalDashboard

## Summary and Conclusions
1. Three visualizations for the final version are shown in Figure 1, Figure 4 and Figure 5.
2. First visualization shows that the number of speed violations are on the decline. Trendline shows violations are decreasing at an average rate of 4.43 violations per day. This will also lead to revenue loss for the City in future, and therefore City should account for the loss in future policy making. It also proves that drivers in general are now more aware of the program and City is also making efforts to make the system efficient.  
3. Second visualization shows that there are some loopholes in the way cameras in School Zones operate in summer months. It is clear from the analysis that, in comparison to August, lot more cameras are operational in July while schools are closed in both July and August. Violations were also illegaly recorded in School Zones on Labor Day holiday. Per City's own rules it is not a legal practice to ticket violaters when schools are closed. This insight will also help the City in decreasing the burden on ticket processing centers and on the courts hearing the ticket appeals.   
4. Third visualization shows that some cameras that report significantly high number of violations have not actually contributed towards reducing number of "Serious Fatal" and "Bicycle Pedestrian"  type crashes. The City should investigate further to make these cameras more effective. 

## References

* Ref 1: The City of Chicago: https://www.chicago.gov/city/en/depts/cdot/provdrs/automated_enforcement/news/2018/july/automated-speed-enforcement-cameras-to-be-activated-in-response-.html
* Ref 2: The City of Chicago: https://www.chicago.gov/content/dam/city/depts/cdot/Red%20Light%20Cameras/2017_Automated_Enforcement_Report20180427.pdf
* Ref 3: Illinois Policy: https://www.illinoispolicy.org/390000-drivers-set-to-receive-refunds-for-red-light-and-speed-camera-tickets/
* Ref 4: Chicago Tribune:  http://apps.chicagotribune.com/news/local/chicago-speed-camera-tickets/cameras/4909-n-cicero-ave/
* Ref 5: https://www.chicagotribune.com/news/watchdog/ct-speed-camera-bad-tickets-met-20151117-story.html
* Ref 6: https://www.chicago.gov/content/dam/city/depts/cdot/CSZ/ASE_CrashAnalysisWriteUp_10_10_18.pdf
