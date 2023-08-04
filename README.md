
<img src="img/city_emblem.png" alt="City Logo"/>

# City of Cape Town - Data Science: Data Analyst Code Challenge

## Purpose

The purpose of this challenge is to evaluate the skills of prospective Data Analysts for positions in the City of Cape Town. 

## Intended audience

We will only evaluate responses to this challenge from people who have been requested to complete it. Of course, you are welcome to attempt it for your own enjoyment.

## Way of working and expected structure of submission
Principles of reproducible analysis and code versioning are very important to our workflow. Structuring your work to aid in reproducibility and readability is important. 

So, follow common conventions with respect to directory structure and names to make your work as easy to follow as possible.

## What we're looking for
### Expectation of Effort
We expect you to spend up to 48 hours working on this assessment. If you are finding that you spending significantly more time than this, then please contact whomever sent you the link to this assessment to let them know.

You should have received over 7 days warning that you would be undertaking this assesment. Please notify [Delyno du Toit](delyno.dutoit@capetown.gov.za) if this was not the case.

### Things to focus on
Over and above the tasks specified below, there are particular aspects that we would like you to pay attention to:

* Data Analyst candidates - we weight success by the degree to which the insights and analysis provided can inform actual decisions. Hence, we want evidence of both the ability to surface these insights from data (trends and outliers), as well as the rhetorical skill in conveying the implications thereof (a clear narrative justified by your analysis and statistical measures). Your audience is intelligent, but not a "technical-specialist".

### Submission outline
You can use any tool to produce the output, e.g. Python, R, Excel, Power BI, Tableau, etc. The final deliverable needs to be a pdf report with your analysis.

## How to submit
1. Download this repository using the Code -> `Download ZIP` option in the top right-hand corner.
2. Download the data from the link below
3. Carry out your analysis and add your work into this folder.
6. Create a ZIP file of this folder, with all of your work in it.
7. Send us an email, attaching your the above ZIP file. If it is larger than 10 MB, then share it via a cloud storage service such as DropBox, and include the link in your email. 

## Challenge
### Data
We have made the following dataset available (the filename is a link). It is available in an AWS bucket [`assessment-data-analyst-sample-data.csv`](https://cct-budgets-code-challenge-input-data.s3.amazonaws.com/opm.assessment-data-analyst-sample-data.csv)

#### Background to the dataset
A virement is defined as the process of transferring an approved budgetary provision from one operating `cost element` to another within a municipal financial year. 

The dataset contains the annual budget allocations, and annual virement "movements", for various directorates, departments and branches of the organisation, broken down by budget `cost_centre` (`category`) and `cost_element` (`sub_category`), over 5 financial years.

**this dataset was generated for the purpose of this exercise and should not be taken to reflect the actual budget allocations within the City of Cape Town**

#### 1. Descriptive Analytic Tasks (if applying for a Data Analyst Position)
Please use the above [dataset](https://cct-budgets-code-challenge-input-data.s3.amazonaws.com/opm.assessment-data-analyst-sample-data.csv) to complete this task.

For the sake of this exercise, assume that the movement of funds after the allocation of the budget (`amount_sent`, `amount_received`) represents an inefficient budget allocation (this is an oversimplification, but will suffice for this exercise), and that `efficient`/`inefficient` refers to how well/poorly the original budget forecasted the actual amount needed for that `cost centre`/`cost-element`.

##### Outputs
**Please provide a "dashboard", in pdf format, that reflects following:**
* a high level view of the trends over time for the net amount sent, as a total amount, and as a percentage of the original budget:
  * at the `directorate` level
  * at the `cost centre` level
  * at the `cost element` level
* Provide a view of the top 5 departments with the highest proportion of `net amount sent` over the last 3 years
* Provide a view of the top 5 departments with the highest proportion of `net amount received` over the last 3 years
* Show the top 5 budget categories (and separetely the top 5 budget sub-categories), taking into account the trends over the past 3 years, for:
  1) the most efficient budget allocations, and
  2) the least efficient budget allocations
 
Your dashboard should also include an `Executive-level summary` section of your analysis and findings. A non-specialist/technical person should be able to understand this summary without additional guidance.

Please include a short text/narrative description of your interpretations/analysis for each of the graphs above.

Please also include any code, and/or spreadsheets used, and any intermediate analysis used to generate the dashboard, in your submission.

## Contact
You can contact gordon.inggs and/or colinscott.anthony @ capetown.gov.za for any questions on the above.
