**Intro**: The HR department serves as the organizational backbone, managing recruitment, employee relations, and performance appraisal while bridging the gap between employees and management. It plays a pivotal role in fostering a healthy work environment and driving organizational success through strategic workforce management.

This dashboard provides a comprehensive overview of key metrics and trends impacting talent acquisition, retention, and employee engagement over the years.

**Dashboard**:

![image](https://github.com/Shibbu91/Bi-Projects/assets/87035922/d77a4fc3-664f-4cb8-9ff0-5bf9734de003)

**DAX Queries**:

Actives = CALCULATE([EmpCount], FILTER(Employee, ISBLANK(Employee[TermDate])))

AVG Tenure Days = ROUND(AVERAGE(Employee[Tenure Days]), 2)

AVG Tenure Months = ROUND([AVG Tenure Days] / 30 ,1 )-1

EmpCount = CALCULATE(COUNT(Employee[EmplID]), FILTER(ALL('Date'[PeriodNumber]), 'Date'[PeriodNumber] = MAX('Date'[PeriodNumber])))

New Hires = SUM(Employee[Is new hire])

Separations = CALCULATE(COUNT(Employee[EmplID]), FILTER(Employee, NOT(ISBLANK(Employee[TermDate]))))

Female Emp Actives = CALCULATE([Actives],Gender[Gender]= "Female")

Female new hires = CALCULATE([New Hires] , Gender[Gender] = "Female" )

Female Separations = CALCULATE([Separations] , Gender[Gender] = "Female")

Male Actives = CALCULATE([Actives] , Gender[Gender] = "Male")

Male New hires = CALCULATE([New Hires] , Gender[Gender] = "Male")

Male Separations = CALCULATE([Separations] , Gender[Gender] = "Male")


