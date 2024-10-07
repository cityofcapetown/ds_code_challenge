
<img src="img/city_emblem.png" alt="City Logo"/>

# City of Cape Town - Urban Mobility Technical Challenge

## Purpose

The purpose of this challenge is to evaluate the skills of prospective Data positions in the City of Cape Town's Urban Mobility directorate. 

## Intended audience

We will only evaluate responses to this challenge from people who we have requested to complete it. Of course, you are welcome to attempt it for your own enjoyment.

## Way of working and expected structure of submission
Principles of reproducible analysis and code versioning are very important to our workflow. Structuring your work to aid in reproducibility and readability is important. 

So, follow common conventions with respect to directory structure and names to make your work as easy to follow as possible.

## What we're looking for
### Expectation of Effort
We expect you to spend up to 48 calendar hours working on this assessment. If you are finding that you are spending significantly more time than this, then please contact whomever sent you the link to this assessment to let them know.

You should have received over 7 days warning that you would be undertaking this assessment. Please notify [Delyno du Toit](delyno.dutoit@capetown.gov.za) if this was not the case.

### Things to focus on
Over and above the tasks specified below, there are particular aspects that we would like you to pay attention to:

Data & Management Information candidates - we weight success by the degree to which the insights and analysis provided can inform actual decisions. Hence, we want evidence of both the ability to surface these insights from data (trends and outliers), as well as the rhetorical skill in conveying the implications thereof (a clear narrative justified by your analysis and statistical measures). Your audience is intelligent, but not a "technical-specialist".

## How to submit
*You can use any tool to produce the output, e.g. Python, R, Excel, Power BI, Tableau, etc.* 
*The **final deliverable needs to be a pdf report** with your analysis.*

1. Download this repository using the Code -> `Download ZIP` option in the top right-hand corner.
2. Download the data from the link below
3. Carry out your analysis and add your work into the downloaded folder.
6. Create a ZIP file of this folder, with all of your work in it.
7. Send us an email, attaching the above ZIP file with your work in it. If it is larger than 10 MB, then share it via a cloud storage service such as DropBox, Google Drive, and include the link in your email. 

## Challenge
*If there are any steps that you can not complete after a reasonable amount of effort, rather move on to later steps, attempting everything relevant at least once.*

#### Data
We have made the following datasets available (each filename is a link). These are all available in an AWS bucket `cct-ds-code-challenge-input-data`, in the `af-south-1` region, with the object name being the filenames below):
* [`sr.csv.gz`](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/sr.csv.gz) contains 12 months of service request data, where each row is a service request. A service request is a request from one of the residents of the City of Cape Town to undertake significant work. This is an important source of information on service delivery, and our performance thereof. *Note* as indicated by the extension, this file is compressed.
* [`sr_hex.csv.gz`](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/sr_hex.csv.gz) contains the same data as `sr.csv` as well as a column `h3_level8_index`, which contains the appropriate resolution level 8 H3 index for that request. If the request doesn't have a valid geolocation, the index value will be `0`. *Note* as indicated by the extension, this file is compressed.
* [`sr_hex_truncated.csv`](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/sr_hex_truncated.csv) is a truncated version of `sr_hex.csv`, containing only 3 months of data.
* [`city-hex-polygons-8.geojson`](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/city-hex-polygons-8.geojson) contains the [H3 spatial indexing system](https://h3geo.org/) polygons and index values for the bounds of the City of Cape Town, at resolution level 8.
* [`city-hex-polygons-8-10.geojson`](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/city-hex-polygons-8-10.geojson) contains the [H3 spatial indexing system](https://h3geo.org/) polygons and index values for resolution levels 8, 9 and 10, for the City of Cape Town.

In some of the tasks below you will be creating datasets that are similar to these, feel free to use the provided files to validate your work.

Each row in the dataset is meant to represent a specific service request

#### Dummy AWS Credentials
We have made AWS credentials available in the following file, with the appropriate permissions set, [here](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/ds_code_challenge_creds.json).

*Note* These creds don't have any special access, other than what is already set on these resources for anonymous access. These are more provided to make using the various AWS client libraries easier.

### Descriptive Analytic Tasks 
*Note:* We are most interested in how you reason about the problem.

Please use the `sr_hex_truncated.csv` dataset to address the following.

For **all** questions outlined below, use the **Urban Mobility directorate** data

**NB**: The **final deliverable** is a report (in PDF form) for the Executive Management team of the City.  An Executive-level, non-specialist should be able to read the report and follow your analysis without guidance.

1. Comment on the quality of the dataset and highlight any data quality issues.
2. In which 3 suburbs should the Urban Mobility directorate concentrate their infrastructure improvement efforts?
   * Outline the logic you used to rank these suburbs
   * Outline the logic you have used to identify issues relating specifically to `infrastructure`.
3. An answer to the questions:
    
    3.1. What is the median & 80th percentile time to complete each service request type across all suburbs for Urban Mobility?
    
    3.2. What is the median & 80th percentile time to complete each service request for the 3 suburbs identified in (2) for Urban Mobility?
    
    3.3. Are there any significant differences in the median and 80th percentile completion times between the City as a whole (3.1) and the 3 suburbs identified in (3.2)?

       * Indicate the criteria used to defined differences as `significant`.
       * Please provide plausable reasoning to explain the similarities or differences identified.
5. Provide a visual `mockup` of a dashboard for the purpose of monitoring progress/improvements from applying the insights identified in (1), (2) and (3).
   * This should focus the user on performance pain points.
   * Each visual element should include a text description, explaining how it helps fulfill this overall function.
   * Provide a set of bullet points to explain how the dashboard would be used (analytical flow across the visual elements) to guide decision making.
6. Identify any duplicate service requests

   5.1. Present a view of these duplicates per service request type.

   5.2. Detail the logic/methodology used to identify duplicates
   
7. Identify value-adding insights for management within Urban Mobility, with regard to potholes.
8. Consider the structure of the raw service request data you worked with above. Provide a recommendation for how you would process, transform, or structure this dataset into an `analytics-ready` dataset.
   * as an additional feature, assuming that the source dataset is extremely large, and that analytical introspection of the data would need to be performant.
   * Provide a visual representation of your recommendation with explanatory text.

## Contact
You can contact gordon.inggs, muhammed.ockards and/or colinscott.anthony @ capetown.gov.za for any questions on the above.
