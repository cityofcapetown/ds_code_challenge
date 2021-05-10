# ds_code_challenge

## Purpose

The purpose of this challenge is to evaluate the skills of prospective Data Scientists, Engineers and Analysts for positions in the City of Cape Town Data Science unit. 

## Intended audience

We will only evaluate responses to this challenge from people who we have requested to complete it. Of course, you are welcome to attempt it for your own enjoyment.


## Way of working and expected structure of submission

Our primary programming languages are `python` and `R`. We will accept code that is packaged in `py`, `.ipynb`, `.R` and `.Rmd` files. Bash is also fine for glue. You may develop in any development environment you choose. 

Principles of reproducible analysis and code versioning are very important to our workflow. Structuring your repo to aid in reproducibility and readability is important - so follow common conventions with respect to directory structure and names.

We expect to be able to clone your repo, immediately identify what script to execute from your README file, and execute it to completion with no human interaction. In order to ensure that our environment has the right libraries or packages, please follow standard python or R guidelines for structurein your code, i.e place `import` and `library()` commands at the top of your script.

If your repo does not clone and run, we will not attempt to fix it.

If your analysis makes use of any external data, the data must either be included in the repo, or be downloaded automatically during script execution.


## How to submit

1. Fork this repository and clone it to your development environment. 
2. Work the challenge, committing regularly to document your progress.
3. Push back to your github remote.
4. Inform us via email that your challenge is complete, including a link to your repo. Be sure to make sure it is set to public.

NOTE: If you would like to _improve_ the content of this repository, by fixing typos or perhaps enhancing the challenge, please do so by submitting a merge request.

## Challenge

For all roles, we expect the challenge response to include what you consider to be role-appropriate testing and validation. For instance, a Data Scientist might want to include MAPE scores or confusion matrices. A Data Engineer may want to include logging and data quality validation tests. A Data Analyst might want to plot histograms of request counts to ensure that outliers aren't overwhelming your analysis.

### If you are interviewing for a Data Science role

In the `data` directory you will find two datasets. `data/sr.csv` contains 36 months of service request data, where each row is a service request. `data/sal.zip` contains Shapefiles of City of Cape Town small area layers. 

1. Time series challenge: Predict the weekly number of expected service requests per small area for the next 4 weeks.
2. Introspection challenge: Reshape the data into number of requests per small area in the last 12 months. Augment this data with any data you may find that is relevant. Predict the number of requests from this augmented data. Determine the drivers of requests of that particular type.
3. Classification challenge: Classify a small area layer as formal, informal or rural based on the data derived from the service request data. NOTE TO CCT: We'll need to pre-classify the SALs.

Feel free to use any other data you can find in the public domain.

**The final output of the execution of your code should be a self contained `html` file or executed `ipynb` file that is your report.** 
 
A statistically minded layperson should be able to read this report and follow your analysis without guidance. 

### If you are interviewing for a Data Analyst role

In the `data` directory you will find a file called `data/sr_sal.csv`. It contains 36 months of service request data, where each row is a service request. The column titled 'SAL' contains the name of the Census 2011 Small Area that the particular request falls under.

1. Provide a visual answer to the question "which areas and request types should Electricity concentrate on to reduce the overall volume of their requests". You may use Jupyter, Rstudio, Excel, PowerBI or Tableau.
2. Provide a working prototype dashboard for monitoring progress in reducing Electricity service request volume per area and per type.

**The final output of the execution of your code should be a self contained `html` file ,executed `ipynb` file, Excel document with appropriate formatting and pivot tables, or PowerBI file.** 
 
An Executive-level person should be able to read this report and follow your analysis without guidance. 

### If you are interviewing for a Data Engineer role

In the `data` directory you will find two datasets. `data/sr.csv` contains 36 months of service request data, where each row is a service request. `data/sal.zip` contains Shapefiles of City of Cape Town small area layers. 

We've provided an uber H3 geoJSON resolution level 8, 9 and 10 file for the City of Cape Town at the following location. [insert readonly object url]. This file will need to be filered for the appropriate resolution prior to joining.

We've also made available an S3 readonly bucket at this location. [Insert here]

1. Create a script which uses AWS S3 SELECT syntax to read in H3 resolution 8 data. Joins it to the service request dataset, select a subset of columns, and write it to the writeonly bucket. Be sure to name your output file something that is recognizable as your work. Include logging that lets the executor know how many of the records failed to join, and include a join error threshold above which the script will error out. 
2. Write a script which anonymizes the sr file, but preserves location accuracy to within approximately 500m, temporal accuracy to within 6 hours, and scrubs any columns which may contain personally identifiable information. You may use H3 indexes or lat/lon coordinates for your spatial data.

**The final output of the execution of your code should be `R`, `python` or `bash` script(s).** 
 
Your code should be well formatted according to generally accepted style guides and include enough commentary for a team-mate unfamiliar with your code to maintain it in your absence.


## Contact

You can contact riaz.arbi, gordon.inggs and/or colinscott.anthony @ capetown.gov.za
