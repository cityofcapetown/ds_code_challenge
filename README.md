
<img src="img/city_emblem.png" alt="City Logo"/>

# City of Cape Town - Data Engineer Code Challenge

## Purpose

The purpose of this challenge is to evaluate the skills of prospective Data Engineers for positions in the City of Cape Town's Data Science unit. 

## Way of working and expected structure of submission
Principles of reproducible analysis and code versioning are very important to our workflow. Structuring your work to aid in reproducibility and readability is important. 

So, follow common conventions with respect to directory structure and names to make your work as easy to follow as possible.

## What we're looking for
### Expectation of Effort
We expect you to spend up to 48 calendar hours working on this assessment per position. If you are finding that you are spending significantly more time than this, then please contact whomever sent you the link to this assessment to let them know.

You should have received over 7 days warning that you would be undertaking this assessment. Please notify [Delyno du Toit](delyno.dutoit@capetown.gov.za) if this was not the case.

### Things to focus on
Over and above the tasks specified below, there are particular aspects of each position that we would like you to pay attention to:

* Data Engineer candidates - as the key enablers of our unit's work, we really want to see work done in a sustainable manner: writing for easy comprehension, testing, clean code, modularity all bring us joy.


Requirements and notes:
* For Data Engineering our primary programming languages are `python`, `R` and `SQL`. We will accept code that is packaged in `.py`, `.ipynb`, `.R` and `.Rmd` files. Scripts in `.sql` may also be included where applicable.
* Bash or similar scripting language files are fine for glue. You may develop in any development environment you choose. 
* We expect to be able to clone your repo, immediately identify what script to execute from your README file, and execute it to completion with no human interaction. 
  In order to ensure that our environment has the right libraries or packages, please follow standard python (PEP8) or R guidelines for structure in your code, i.e place `import` and `library()` commands at the top of your scripts.
* If your repo does not clone and run, we will not attempt to fix it.
* If your analysis makes use of any external data, the data must either be included in the repo, or be downloaded automatically during script execution.

## How to submit
1. Clone this repository and load it into your development environment. 
2. Work the challenge, committing regularly to document your progress. Try have structured, meaningful commits, where each one adds significant functionality in a coherent manner.
3. Host your repository somewhere that is publicly accessible. If you're using GitHub, please use a fork of our original repository.
4. Inform us via email that your challenge is complete, including a link to your repo. Be sure to make sure it is set to public.

**Be sure to 'watch' this repo for changes - we may push bugfixes**

NOTE: If you would like to _improve_ the content of this repository, by fixing typos or perhaps enhancing the challenge, please do so by submitting a pull request.

## Challenge
Follow the below steps. If there are any steps that you can not complete after a reasonable amount of effort, rather move on to later steps, attempting everything relevant at least once.

We expect the challenge response to include what you consider to be role-appropriate testing and validation. For example, a Data Engineer may want to include logging and data quality validation tests, as well as unit and even integration tests. 

Your code should be well formatted according to generally accepted style guides and include whatever is necessary for a team-mate unfamiliar with it to maintain it.

### 0. Setup
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

### 1. Data Extraction 
Use the [AWS S3 SELECT](https://docs.aws.amazon.com/AmazonS3/latest/userguide/s3-glacier-select-sql-reference-select.html) command to read in the H3 resolution 8 data from `city-hex-polygons-8-10.geojson`. Use the `city-hex-polygons-8.geojson` file to validate your work.

Please log the time taken to perform the operations described, and within reason, try to optimise latency and computational resources used. Please also note the comments above about the nature of the code that we expect.

### 2. Initial Data Transformation 
Join the equivalent of the contents of the file `city-hex-polygons-8.geojson` to the service request dataset, such that each service request is assigned to a single H3 resolution level 8 hexagon. Use the `sr_hex.csv.gz` file to validate your work.

For any requests where the `Latitude` and `Longitude` fields are empty, set the index value to `0`.

Include logging that lets the executor know how many of the records failed to join, and include a join error threshold above which the script will error out. Please motivate why you have selected the error threshold that you have. Please also log the time taken to perform the operations described, and within reason, try to optimise latency and computational resources used.

### 3. Further Data Transformations
1. Create a subsample of the data by selecting all of the requests in `sr_hex.csv.gz` which are within 1 minute of the centroid of the BELLVILLE SOUTH official suburb. You may determine the centroid of the suburb by the method of your choice, but if any external data is used, your code should programmatically download and perform the centroid calculation. Please clearly document your method.

2. Augment your filtered subsample of `sr_hex.csv.gz` from (1) with the appropriate [wind direction and speed data for 2020](https://www.capetown.gov.za/_layouts/OpenDataPortalHandler/DownloadHandler.ashx?DocumentName=Wind_direction_and_speed_2020.ods&DatasetDocument=https%3A%2F%2Fcityapps.capetown.gov.za%2Fsites%2Fopendatacatalog%2FDocuments%2FWind%2FWind_direction_and_speed_2020.ods) from the Bellville South Air Quality Measurement site, from when the notification was created. All of the steps for downloading and preparing the wind data, as well as the join should be performed programmatically within your script.

3. Write a script which anonymises your augmented subsample from (2), but preserves the following precisions (You may use H3 indice or lat/lon coordinates for your spatial data):
   * location accuracy to within approximately 500m
   * temporal accuracy to within 6 hours
Please also remove any columns which you believe could lead to the resident who made the request being identified. We expect in the accompanying report that you will justify as to why this data is now anonymised. Please limit this commentary to less than 500 words. If your code is written in a code notebook such as Jupyter notebook or Rmarkdown, you can include this commentary in your notebook.

## Contact
You can contact gordon.inggs, muhammed.ockards and/or colinscott.anthony @ capetown.gov.za for any questions on the above.
