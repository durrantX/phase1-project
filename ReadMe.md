Final Project Submission

Student name: Deon Durrant

Aviation_Dashboard https://public.tableau.com/views/AviationAnalysisDSCProject/Aviation_Dashboard?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

# Overview 
The project analyzes historical Aviation Accident Database & Synopse dataset to inform Company Y regarding diversification into the aviation industry. Company Y will utilize the analysis to determine airplane risk and key stakeholders tolerance  along with other metrics beyond the scope of this project.
# Business Problem
Company Y portfolio diversification maybe possible when airplane safety is aligned with not just asset damage but more closely with the community consequences. Identifying the risk or the riskiest models and aircraft, the occurrence of accidents and the extremes of human cost that is fatality versus non injury. Using the aviation accident data, I analyzed trends and patterns of accidents; fatalities; non-injury(uninjured); purpose of flight; country, and airplane engine type, make and model.

# Data Understanding
The aviation accident data set is a global public data set of accidents and incidents since 1979. Each event year has unique ID's associated with fatalities, country and injuries including categorical data such as aircraft type make model etc..


# Initial exploratory data analysis
Import data and convert to pandas dataframe
Explore and examine the data 
Examine the data structure.

# Summary of the overall structure of dataframe
The data summary confirms this is a pandas dataframe. The dataframe has 90348 entries within 31 columns
Indication of missing data in 30  of the columns.Decisions regarding handling of such is taken during data cleaning.
dtypes: float64(5), object(26)
memory usage: 21.4+ MB



# To answer business question and  make recommendations 
1. Focus exclusively on airplanes within the aircraft category
2. Analysis will encompass accidents per year, categorized by country, fatalities, and uninjured individuals
3. Examine the relationship between the number of accidents and aircraft make, model and engine type
4. Delve into the connection between aircraft attributes fatalities and uninjured individuals
5. Analayze data related to the purpose of flight, including accident statistics, fatalities, and uninjured individuals
6. Analysis will include both the commercial and private business segments, as these are of interest to the company 

# Columns for analysis 
['Investigation.Type', ''Event.Date''Injury.Severity', 'Engine.Type', Aircraft.Category''Make', 'Model''Purpose.of.flight 'Total.Fatal.Injuries', 'Total.Serious.Injuries', 'Total.Minor.Injuries', 'Total.Uninjured']

# Aviation Data Dictionary

Column Name	           Short Description	           Meaning

InvestigationType	   Type of Event	      Refers to a regulatory definition of the event severity. The severity of a general aviation accident or incident is classified as the combination of the highest level of injury sustained by the personnel involved (that is, fatal, serious, minor, or none) and level of damage to the aircraft involved (that is, destroyed, substantial, minor, or none). The

EventDate	Event Date	The date of the event. Dates are be entered in the format: MM/DD/YYYY
Country	Event Country	The country in which the event took place.

AircraftCategory	   Aircraft Category	The category of the involved aircraft. In this case, the definition of aircraft category is the same as that used with respect to the certification, ratings, privileges, and limitations of airmen. Also note that there is some overlap of category and class in the available choices.

Make	Aircraft Manufacturer's Full Name	Name of the manufacturer of the involved aircraft.

Model	Aircraft Model	The full alphanumeric aircraft model code, including any applicable series or derivative identifiers. For example, a 200 series Boeing 737 is entered as 737-200.



# DATA CLEANING


# Business is interested in one category of aircrafts: airplane
 New dataframe includes rows containing airplanes only.


# Data Type Conversion
1.Change  date format and dtype

2.Change Event.Date to Event.Year

3.Change Event.Year to string 

4.Drop Event.Date column


# Handling Missing Data:
1. Evaluate for missing data
2. Missing categorical data for 'Purpose of Flight' if deleted may remove valuable information required for decison making.Create new category 'Unknown'instead.
3. Missing categorical data for 'Engine Type' removed
4. Missing numerical values will be replaced by the mean

# Handling Inconsistent Data: 
Adrress typos, variations in capitalization, and naming conventions

# Analyzing the data and building visualizations


#According to Annex 5, "an incident is defined as an occurrence, other than an accident, associated with the operation of an aircraft which affects or could affect the safety of operation".

#Accident is defined as "accident as an occurrence associated with the operation of an aircraft: in which a person is fatally or seriously injured; in which an aircraft sustains damage or structural failure requiring repairs; after which the aircraft in question is classified as being missing.#"

#https://applications.icao.int/postalhistory/annex_13_aircraft_accident_and_incident_investigation.htm#:~:text=Annex%2013%20outlines%20how%20accident,following%20completion%20of%20the%20investigation.

In alignment with the FAA definition of Accident analyses will be done only on this subset.


 
# The human cost: fatalities and injuries through the years

Findings - Human Cost for Year

In terms of assessing the human cost for each year, the number of fatalities peaked in 2010 followed by a decline as the number of uninjured individuals increased peaking in 2011. 
Throughout the timeframe there is an approximate ratio of 8.8 uninjured to every fatality. This is indicative of a certain level of confidence regarding safety when the mode of transportation is airplane.

![image](https://github.com/durrantX/phase1-project/assets/148919288/a233ce0e-5e5b-4b33-ae40-e2d01696bd73)






# Groupby Country
Grouping by country allows for examination of the geographical aspect and categorize accidents , fatalities and uninjured individuals

![image](https://github.com/durrantX/phase1-project/assets/148919288/67a29d98-42a3-401c-a3f7-08e9115e6bbd)









 # Community Consequences 
Considering the community consequences, the United States leads in terms of accidents, with Brazil trailing significantly behind. It is noteworthy that the United States also records the highest rates of fatalities, injuries, and non-injured individuals, which aligns with its larger number of accidents throughout the data period.
Intriguingly, among the top thirty countries, 100% of Lebanon's and 97% of Libya's records consist of fatalities. Furthermore, the United States stands out as the only country within the top five rankings for both fatalities and uninjured individuals.



 # Groupby Purpose of Flight
 Grouping by the flights by the intended  purpose enables analysis of the business segment and categorize accidents , fatalities and uninjured individuals


![image](https://github.com/durrantX/phase1-project/assets/148919288/97157604-9f41-46ce-9f86-634fb494b0d1)










# Personal and Social Consequences
In terms of personal and social consequences, a noteworthy number of fatalities are associated with trips categorized as 'Personal.'
Interestingly, the 'Unknown' category stands out with the second highest rates of both fatalities and uninjured individuals. It's important to note that the 'Unknown' subset was created to account for missing data. When this 'Unknown' subset is excluded, the top five safest categories, based on the aggregate number of uninjured individuals, are 'Personal,' 'Business,' 'Instructional,' 'Aerial Application,' and 'Skydiving.'
Notably, there have been no recorded fatalities for the 'AirDrop' and 'PUBS' subsets."



# Examine the actual aircraft data
Groupby aircraft model
Groupby aircraft make
Groupby aircraft engine type 


# Groupby aircraft make

![image](https://github.com/durrantX/phase1-project/assets/148919288/b4d42d98-347d-40de-9247-f0b73ac887da)







# Make
The airplane Make with the highest accident rates are Cessna, Piper, Beech and Boeing. 
Highest fatalities for Make are Cessna, Boeing, Piper and Airbus
The 'Make' with the most uninjured are Boeing Cessna, Airbus and McDonnell Douglas


# Groupby Engine type
 Grouping the data by engine type enables examination of the connection between this aircraft attribute, fatalities and uninjured individuals. 

![image](https://github.com/durrantX/phase1-project/assets/148919288/53c88089-14fc-4ea6-86ac-4c0897169f92)






# Findings
Within the aircraft engine type  categories, Reciprocating engine stands out with the highest number of accidents followed by Turbo prop, Turbo Fan, and Turbo Jet.

The reciprocating engine stands out with the highest number of fatalities followed by Turbo Prop, Turbo Fan, and Unknown. 
The Turbo Fan  leads with the highest count of uninjured individuals,followed by the Reciprocating and Turbo Jet engines. 




# Groupby Make and Model







![image](https://github.com/durrantX/phase1-project/assets/148919288/71539573-0636-4af3-8761-0889cc0c40e1)


# Findings
In the combined analysis of aircraft make and model, Cessna holds the top six positions with the highest number of accidents, suggesting a higher propensity for accidents in this category.
 Boeing secures the top five positions with the highest number of uninjured individuals, indicating a higher level of safety within this category. Boeing 737 ranked number one most uninjured individuals. 
In the thorough examination  of aircraft make and model, Boeing 747-300 ocupies the top  position with the highest number of fatalities, suggesting a lower level of safety within this category. 



# Impact on lives
In the comprehensive analysis of aircraft purpose of flight, make, and model, Cessna's various models exhibit strong associations with specific flight purposes, notably in the 'Personal' and 'Instructional' subsets. Noticeably, the Cessna 172 is recognized as one of the top ten safest airplane.



# Conclusion 

1.	When evaluating the human cost over the years, fatalities reached their peak in 2010, followed by a decline as the number of uninjured individuals increased, reaching its peak in 2011. Throughout this period, there is an approximate ratio of 8.8 uninjured individuals for every fatality. This suggests a notable level of confidence in aviation safety.


2.	Among the top ten countries worldwide in terms of uninjured individuals, the United States leads with the highest number, and Puerto Rico, a U.S. territory, is among the top five countries.

3.	In the category of aircraft Make, Boeing takes the lead with the highest number of uninjured individuals, followed by Cessna, Airbus, and Piper. This reflects the least human consequences.

4.	Among aircraft models, the 737 stands out with the highest number of individuals who did not sustain injuries.

5.	Within the aircraft engine type categories, Turbo Fan engines lead with the highest count of uninjured individuals, followed by Reciprocating and Turbo Jet engines.

6.	In a comprehensive analysis of aircraft make and model, Boeing secures the top five positions with the highest number of uninjured individuals, indicating a higher level of safety in this category, with the Boeing 737 ranking as number one for the most uninjured individuals.

7.	Excluding the 'Unknown' subset, the top five safest categories, based on the aggregate number of uninjured individuals, are 'Personal,' 'Business,' 'Instructional,' 'Aerial Application,' and 'Skydiving.' It's worth noting that there have been no recorded fatalities for the 'AirDrop' and 'PUBS' subsets.

8.	In a thorough analysis of aircraft intended purpose of flight, make, and model, Cessna's various models show strong associations with specific flight purposes, especially in the 'Personal' and 'Instructional' subsets. Notably, the Cessna 172 ranks as one of the top ten safest airplanes.


For More Information
See the full analysis in the Jupyter Notebook or review this presentation.


# Data structure 

data


Aviation Data Analysis.ipynb

ReadMe.md

presentation.pdf
