# Pewlett Hackard Analysis
An analysis of the Pewlett Hackard employee database

## Overview
The purpose of this analysis is to determine the number of potential retirees from the company in order to inform the management of the need for new hires.  Some departments intend to start a mentorship program in order to utilize the expertise of current employees that are approaching retirement age.

## Results
Pewlett Hackard is a large and established company with many employees reaching retirement age. Preparation should begin right away as these employees will need to be replaced in order to keep up with demand and maintain productivity. Some points of interest are:
* There are 90, 398 employees that could potentially be retiring in the near future
* Of those employees retiring, only 2 appear to be managers. Quite conspicuous for such a large company.
* The total number of employees at Pewlett Hackard is 300, 024, so about 30% will be retiring soon.
* The mentor program qualifies a meager 1,549 employees.

## Summary
The roles that must be filled in the near future is immense.  Nearly a third of the employees will need to be replaced. It seems that the mentorship program will most likely need to recruit many more employees than those that have currently qualified. However, an ideal mentor would be highly experienced and knowledgeable. I may be worth limiting the mentors to the Senior Staff and Senior Engineers. To do this we can add the following line to a query selection of the mentorship eligibility table:

WHERE mentorship_eligibility.title = 'Senior Engineer' OR mentorship_eligibility.title = 'Senior Staff'

This will narrow the pool of mentors, but will increase the suitability for the job. To offset this, perhaps we can expand the age range of those that qualify. Increasing the birth dates from 1965 only to two years before and two years after. To accomplish this with a query we can amend the query which creates the mentorship eligibility table.

### From:
AND e.birth_date BETWEEN  '1965-01-01'  AND  '1965-12-31'
### To:
AND e.birth_date BETWEEN  '1963-01-01'  AND  '1967-12-31'
