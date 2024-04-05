
<img src="img/city_emblem.png" alt="City Logo"/>

# City of Cape Town - Data Science: Data Analyst Code Challenge

## Purpose

The purpose of this challenge is to evaluate the skills of prospective Data Analysts for positions in the City of Cape Town. 

## Intended audience

We will only evaluate responses to this challenge from people who have been requested to complete it. Of course, you are welcome to attempt it for your own enjoyment.

## Way of working and expected structure of submission
**Principles of reproducible analysis and code versioning are very important to our workflow. Structuring your work to aid in reproducibility and readability is important.**

So, follow common conventions with respect to directory structure and names to make your work as easy to follow as possible.

## What we're looking for
### Expectation of Effort
We expect this assessment to take no more than 24 hours. If you are finding that you spending significantly more time than this, then please contact whomever sent you the link to this assessment to let them know.

You should have received over 7 days warning that you would be undertaking this assesment. Please notify [Delyno du Toit](delyno.dutoit@capetown.gov.za) if this was not the case.

### Things to focus on
Over and above the tasks specified below, there are particular aspects that we would like you to pay attention to:

* Data Analyst candidates - we weight success by the degree to which the insights and analysis provided can inform actual decisions. Hence, we want evidence of both the ability to surface these insights from data (trends and outliers), as well as the rhetorical skill in conveying the implications thereof (a clear narrative justified by your analysis and statistical measures). Your audience is intelligent, but not a "technical-specialist".

### Submission outline
You can use any tool to produce the final output, e.g. Python, R, Excel, Power BI, Tableau, etc. The final deliverable needs to be a pdf report with your analysis.

## How to submit
1. Download this repository using the Code -> `Download ZIP` option in the top right-hand corner.
2. Download the data from the link below
3. Carry out your analysis and add your work into the downloaded folder.
6. Create a ZIP file of this folder, with all of your work in it.
7. Send us an email, attaching the above ZIP file with your work in it. If it is larger than 10 MB, then share it via a cloud storage service such as DropBox, and include the link in your email. 

## Challenge
### Data
We have made the following dataset available (the filename is a link). It is available in an AWS bucket [`assessment-data-analyst-sample-data.csv`](https://cct-budgets-code-challenge-input-data.s3.amazonaws.com/opm.assessment-data-analyst-sample-data.csv)

#### Background to the dataset
Budget is allocated to different levels of the organisational hierarchy: Directorates/Departments etc. for a number of different categories (contract work, employee wages, purchasing materials etc.)

Operational needs can change over time, hence managers need a way to adjust their budget structure in line with these changing needs.

A virement is a mechanism to provide this flexibility and is defined as the process of transferring a budget allocated to one item category (called a `cost element`) to another, or to another organisational unit (`cost centre`) within a directorate in a given municipal financial year (July to June). 

This allows managers to ensure they do not overspend in a particular budget category and keep the planned expenditure in line with the actual needs. 

However, it can also signal that the initial budget allocation was not efficient.

The dataset provided contains the annual budget allocations, and annual virements "movements", for different levels of the organisatinoal hierarchy (directorates, departments and branches), further broken down by the organisational unit  within the hierachy (`cost_centre`) and the budget item category (`cost_element`), over 5 financial years.

**this dataset was generated for the purpose of this exercise and does not reflect the actual budget allocations within the City of Cape Town**

### 1. Descriptive Analytic Tasks (if applying for a Data Analyst Position)
Please use the above [dataset](https://cct-budgets-code-challenge-input-data.s3.amazonaws.com/opm.assessment-data-analyst-sample-data.csv) to complete this task.

For the sake of this exercise, assume that the each virement/movement of funds represents an inefficient budget allocation, and that `efficient`/`inefficient` refers to how well/poorly the original budget forecasted the actual amount needed for that `cost centre`/`cost-element` (this is an over-simplification, but will suffice for the exercise).

#### Outputs
The main output is a "dashboard", in pdf format
* In addition to the pdf dashboard, please also include any code, and/or spreadsheets, and any intermediate analysis, used to generate the dashboard, in your submission.
* Your analysis should be accompanied by a short text/narrative explanation of your reasoning/findings
* A non-specialist/technical person should be able to understand this without additional guidance.

**Your dashboard must include the following** 
1) A high level view of the trends over time for the net amount moved, as a total amount, and as a percentage of the original budget:
  * at the `directorate` level
  * at the `cost centre` level
  * at the `cost element` level
* Provide a short text/narrative description to explain your analysis, how you identified the items and what these values may mean
  
2) A view of the top 5 departments with the highest proportion of `net amount moved` over the last 3 years

3) Show the top 5 budget item categories (cost elements) in the most recent financial year, for:
  1) the most efficient budget allocations, and
  2) the least efficient budget allocations
* Provide a short text/narrative description to explain your analysis, how you identified the items and what these values may mean

4) A summmary figure or table with a narrative to highlight 2 budget changes that your analysis suggest would improve the budget allocation efficiency

5) A one pararaph executive summary of your findings

## Contact
You can contact gordon.inggs @ capetown.gov.za for questions relating to access to the data and colinscott.anthony @ capetown.gov.za for any questions relating to the analysis tasks.
