
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

#### Dummy AWS Credentials
We have made AWS credentials available in the following file, with the appropriate permissions set, [here](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/ds_code_challenge_creds.json).

*Note* These creds don't have any special access, other than what is already set on these resources for anonymous access. These are more provided to make using the various AWS client libraries easier.

### Descriptive Analytic Tasks 
*Note:* We are most interested in how you reason about the problem.

Please use the `sr_hex_truncated.csv` dataset to address the following.

Please provide the following - **Focus on the Urban Mobility directorate**:
1. Comment on the quality of the dataset and highlight any issues.
2. An answer to the question "In which 3 suburbs should the Urban Mobility directorate concentrate their infrastructure improvement efforts?".

   Please motivate how you related the data provided to infrastructure issues.
3. An answer to the questions:
    1. "What is the median & 80th percentile time to complete each service request across the City?" (each row represent a service request).
    2. Focusing on the Urban Mobility directorate - "What is the median & 80th percentile time to complete each service request for the 3 suburbs identified in (1)?" (each row represent a service request).
    3. "Is there any significant differences in the median and 80th percentile completion times between the City as a whole and the 3 suburbs identified in(1)?".  Please elaborate on the similarities or differences.
4. Provide a visual mockup of a dashboard for the purpose of monitoring progress in applying the insights developed in (1) & (2). It should focus the user on performance pain points. Add a note for each visual element, explaining how it helps fulfill this overall function. Please also provide a brief explanation as to how the data provided would be used to realise what is contained in your mock.
5. Identify duplicate service requests and
   1. Present a view of these duplicates per service request type.
   2. Comment on the methodology you followed to identify these duplicates
6. Identify value-adding insights for the management of Urban Mobility, from the dataset provided, in regard to waste collection within the City.
 
The **final deliverable** is a report (in PDF form) for the Executive Management team of the City.  An Executive-level, non-specialist should be able to read the report and follow your analysis without guidance.

## Contact
You can contact gordon.inggs, muhammed.ockards and/or colinscott.anthony @ capetown.gov.za for any questions on the above.
