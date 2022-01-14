### Project 1: SAT Score analysis 

---

In this project, I studied the trends of SAT scores of all 50 states in the USA, from 2017 to 2021. The objective is to verify the extent of impact Covid-19 has on a student's eligibility to get into college.  The findings will then be used to highlight states which have performed well/poorly.

Data used for this project:
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))
* [`sat_2020.csv`](../data/sat_2020.csv): 2020 SAT Scores by State  ([*source*](https://worldpopulationreview.com/state-rankings/sat-scores-by-state))
* [`sat_2021.csv`](../data/sat_2021.csv): 2021 SAT Scores by State ([*source*](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))
* [`sat_act_by_college.csv`](./data/sat_act_by_college.csv): Ranges of Accepted ACT & SAT Student Scores by Colleges ([source](https://www.compassprep.com/college-profiles/))

### Summary & Key Findings
---
* Despite the lockdowns, 34 of 50 states managed to maintain a relatively consistent score since 2017. Only 3 states had a significant drop in scores. 
* While Covid resulted in new 5-year low scores for 20 states, more than half of them were 10 points or less. 
* However, urgent attention is needed for 19 states, as their scores are eligible for 1 or less colleges/universities' popular/competitive course.

Covid has had an effect on the state's performance. However, the root cause of students being unable to secure a placement cannot be attributed to Covid alone since more than half of the state scores were relatively consistent since 2017.

### Data Dictionary
---

#### state_lkp
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**states_of_usa**|*str*|state_lkp|Name of state|
|**postal_of_states**|*str*|state_lkp|postal of states|

#### sat_scores
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**postal_of_states**|*str*|sat_scores|postal code of state|
|**state**|*str*|sat_scores|Name of state|
|**reading**|*int*|sat_scores|state-averaged evidence based reading and writing score|
|**math**|*int*|sat_scores|state-averaged math score|
|**year**|*int*|sat_scores|year in which the test was taken|

#### college_accept_lkp_2021
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**school**|*str*|college_accept_lkp_2021|name of college|
|**year**|*int*|college_accept_lkp_2021|year of admissions data|
|**sat_total_25percentile**|*float*|college_accept_lkp_2021|25 percentile of SAT Total admission scores|
|**sat_total_75percentile**|*float*|college_accept_lkp_2021|75 percentile of SAT Total admission scores|

#### state_poor_performer
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*str*|state_poor_performer|name of state|
|**postal_of_states**|*str*|state_poor_performer|postal code of state|
|**category**|*str*|state_poor_performer|type of subject|
|**2017_2019_min**|*float*|state_poor_performer|pre-covid all-time low|
|**2020_2021_min**|*float*|state_poor_performer|post-covid all-time low|
|**is_poor_performer**|*bool*|state_poor_performer|flag value; True, if post-covid all-time low is worse than pre-covid all-time low|

#### accept_table
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*str*|accept_table|name of state|
|**count**|*int*|accept_table|number of colleges eligible, by 75percentile|
|**percent_eligible**|*float*|accept_table|percentage of colleges eligible, out of the list provided|
