
<img src="img/city_emblem.png" alt="City Logo"/>

# City of Cape Town - Data Science Unit Code Challenge

## Purpose

The purpose of this challenge is to evaluate the skills of prospective Data Scientists, Engineers and Analysts for positions in the City of Cape Town's Data Science unit. 

## Intended audience

We will only evaluate responses to this challenge from people who we have requested to complete it. Of course, you are welcome to attempt it for your own enjoyment.

## Way of working and expected structure of submission
Principles of reproducible analysis and code versioning are very important to our workflow. Structuring your work to aid in reproducibility and readability is important. 

So, follow common conventions with respect to directory structure and names to make your work as easy to follow as possible.

### Candidates where programming is required (Data Scientist and Engineers)
Requirements and notes:
* Our primary programming languages are `python` and `R`. We will accept code that is packaged in `py`, `.ipynb`, `.R` and `.Rmd` files. 
* Bash or similar scripting language files are fine for glue. You may develop in any development environment you choose. 
* We expect to be able to clone your repo, immediately identify what script to execute from your README file, and execute it to completion with no human interaction. 
  In order to ensure that our environment has the right libraries or packages, please follow standard python (PEP8) or R guidelines for structure in your code, i.e place `import` and `library()` commands at the top of your scripts.
* If your repo does not clone and run, we will not attempt to fix it.
* If your analysis makes use of any external data, the data must either be included in the repo, or be downloaded automatically during script execution.

### Candidates where programming is not required (Data Analysts)
*NB* If you prefer, you may submit using the requirements described above.

The final output of your analysis should be either a self-contained `html` file, executed `ipynb` file, 
Excel document with appropriate formatting and pivot tables, or a PowerBI file.

## How to submit
### Candidates where programming is required (Data Scientist and Engineers)
1. Clone this repository and load it into your development environment. 
2. Work the challenge, committing regularly to document your progress. Try have structured, meaningful commits, where each one adds significant functionality in a coherent manner.
3. Host your repository somewhere that is publicly accessible. If you're using GitHub, please use a fork of our original repository.
4. Inform us via email that your challenge is complete, including a link to your repo. Be sure to make sure it is set to public.

NOTE: If you would like to _improve_ the content of this repository, by fixing typos or perhaps enhancing the challenge, please do so by submitting a merge request.

### Candidates where programming is not required (Data Analysts)
*NB* If you prefer, you may submit using the workflow described above.
1. Download this repository using the Code -> `Download ZIP` option in the top right-hand corner.
2. Add your work into this folder.
3. Create a compressed archive file with all of your work in it.
4. Send us an email, with your archived project attached. If it is larger than 10 MB, then share it via a cloud storage service such as DropBox, and include the link in your email. 

## Challenge
Follow the below steps, completing those indicated as relevant to the positions for which you are interviewing. If there are any steps that you can not complete after a reasonable amount of effort, rather move on to later steps, attempting everything relevant at least once.

For all roles, we expect the challenge response to include what you consider to be role-appropriate testing and validation. For example, a Data Scientist might want to include MAPE scores or confusion matrices. A Data Engineer may want to include logging and data quality validation tests. A Data Analyst might want to plot histograms of request counts to ensure that outliers aren't overwhelming your analysis.

Your code should be well formatted according to generally accepted style guides and include whatever is necessary for a team-mate unfamiliar with it to maintain it.

### 0. Setup
In the `data` directory you will the following datasets:
* `sr.csv` contains 36 months of service request data, where each row is a service request. A service request is a request from one of the residents of the City of Cape Town to undertake significant work. This is an important source of information on service delivery, and our performance thereof.
* `city-hex-polygons-8.geojson` contains polygons and index values for the [H3 spatial indexing system](https://h3geo.org/) for the bounds of the City of Cape Town, at resolution level 8.
* `sr_hex.csv` contains the same data as `sr.csv` as well as a column `h3_level8_index`, which contains the appropriate resolution level 8 H3 index for that request. If the request doesn't have a valid geolocation, the index value will be `0`.

In some of the tasks below you will be creating datasets that are similar to these, feel free to use them to validate your work.

### 1. Data Extraction (if applying for Data Engineering Positions)
We have made two resources available remotely:
* A GeoJSON file that contains the level 8, 9 and 10 resolution hexagons for the City of Cape Town at [this location](https://cct-ds-code-challenge-input-data.s3.af-south-1.amazonaws.com/city-hex-polygons-8-10.geojson) (bucket name is `cct-ds-code-challenge-input-data`, object name is `city-hex-polygons-8-10.geojson`, region is `af-south-1`).
* An AWS S3 writeonly bucket at [this location](https://cct-ds-code-challenge-output-data.s3.af-south-1.amazonaws.com/) (bucket name is `cct-ds-code-challenge-output-data`).

Using [AWS S3 SELECT](https://docs.aws.amazon.com/AmazonS3/latest/userguide/s3-glacier-select-sql-reference-select.html) syntax to read in H3 resolution 8 data from this file. Use the `city-hex-polygons-8.geojson` file to validate your work.

Please log the time taken to perform the operations described, and within reason, try to optimise latency and computational resources used.

### 2. Initial Data Transformation (if applying for Data Engineering and/or Science Positions)
Join the file `city-hex-polygons-8.geojson` to the service request dataset, such that each service request is assigned to a single H3 hexagon. Use the `sr_hex.csv` file to validate your work.

For any requests where the `Latitude` and `Longitude` fields are empty, set the index value to `0`.

Include logging that lets the executor know how many of the records failed to join, and include a join error threshold above which the script will error out. Please also log the time taken to perform the operations described, and within reason, try to optimise latency and computational resources used.

### 3. Descriptive Analytic Tasks (if applying for Data Science and/or Analyst Positions)
Please provide the following:
1. Provide a visual answer to the question "which areas and request types should Electricity concentrate on to reduce the overall volume of their requests".
2. Provide a working prototype dashboard for monitoring progress in reducing Electricity service request volume per area, and per type.
 
An Executive-level person should be able to read this report and follow your analysis without guidance.

### 4. Predictive Analytic Tasks (if applying for Data Science Positions)
Please chose two of the following:
1. *Time series challenge*: Predict the weekly number of expected service requests per hex for the next 4 weeks.
2. *Introspection challenge*: Reshape the data into number of requests, per type, per hex in the last 12 months. Chose a particular request type, or group of requests. Develop a model that predicts the number of requests of your selected type, using the rest of your data. Based upon the model, and any other analysis, determine the drivers of requests of that particular type(s).
3. *Classification challenge*: Classify a hex as formal, informal or rural based on the data derived from the service request data.

Feel free to use any other data you can find in the public domain, except for task (3).

**The final output of the execution of your code should be a self-contained `html` file or executed `ipynb` file that is your report.** 
 
A statistically minded layperson should be able to read this report and follow your analysis without guidance.https://h3geo.org/

Please log the time taken to perform the operations described, and within reason, try to optimise latency and computation resources used.

### 5. Further Data Transformations (if applying for Data Engineering Positions)
Write a script which anonymises the `sr.csv` file, but preserves the following resolutions (You may use H3 indexes or lat/lon coordinates for your spatial data):
   * location accuracy to within approximately 500m 
   * temporal accuracy to within 6 hours
   * scrubs any columns which may contain personally identifiable information.

We expect in the accompanying report that follows you will justify as to why this data is now anonymised.

### 6. Data Loading Tasks (if applying for Data Engineering Positions)
Select a subset of columns (including the H3 index column) from the `sr_hex.csv` or the anonymised file created in the task above, and write it to the write-only S3 bucket. 

Be sure to name your output file something that is recognisable as your work, and unlikely to collide with the names of others.

## Contact
You can contact riaz.arbi, gordon.inggs and/or colinscott.anthony @ capetown.gov.za for any questions on the above.
