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
* Bash scripts are fine for glue. You may develop in any development environment you choose. 
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

For all roles, we expect the challenge response to include what you consider to be role-appropriate testing and validation. For instance, a Data Scientist might want to include MAPE scores or confusion matrices. A Data Engineer may want to include logging and data quality validation tests. A Data Analyst might want to plot histograms of request counts to ensure that outliers aren't overwhelming your analysis.

### If you are interviewing for a Data Science role

In the `data` directory you will find two datasets:
* `data/sr.csv` contains 36 months of service request data, where each row is a service request.  A service request is a request from one of our residents to undertake significant work.
* `data/sal.zip` contains Shapefiles of City of Cape Town small area layers. 

1. *Time series challenge*: Predict the weekly number of expected service requests per small area for the next 4 weeks.
2. *Introspection challenge*: Reshape the data into number of requests per small area in the last 12 months. Augment this data with any data you may find that is relevant. Predict the number of requests from this augmented data. Determine the drivers of requests of that particular type.
3. *Classification challenge*: Classify a small area layer as formal, informal or rural based on the data derived from the service request data. NOTE TO CCT: We'll need to pre-classify the SALs.

Feel free to use any other data you can find in the public domain.

**The final output of the execution of your code should be a self contained `html` file or executed `ipynb` file that is your report.** 
 
A statistically minded layperson should be able to read this report and follow your analysis without guidance. 

### If you are interviewing for a Data Analyst role

In the `data` directory you will find a file called `data/sr_sal.csv`. It contains 36 months of service request data, where each row is a service request. A service request is a request from one of our residents to undertake significant work. The column titled 'SAL' contains the name of the Census 2011 Small Area that the particular request falls under.

1. Provide a visual answer to the question "which areas and request types should Electricity concentrate on to reduce the overall volume of their requests".
2. Provide a working prototype dashboard for monitoring progress in reducing Electricity service request volume per area and per type.
 
An Executive-level person should be able to read this report and follow your analysis without guidance. 

### If you are interviewing for a Data Engineer role

In the `data` directory you will find a dataset file, `data/sr.csv`, which contains 36 months of service request data, where each row is a service request. A service request is a request from one of our residents to undertake significant work.

We have made two resources available remotely:
* A GeoJSON file that contains the level 8, 9 and 10 resolution hexagons for the City of Cape Town at [this location](insert readonly object url).
* An AWS S3 writeonly bucket at [this location](Insert here).

1. *Extraction and Load Challenge* - create a script which joins the SR data to the H3 hex data, meeting the following requirements:
   1. Uses AWS S3 SELECT syntax to read in H3 resolution 8 data. 
   2. Joins it to the service request dataset
   3. Select a subset of columns (including the H3 index column), and write it to the writeonly bucket. Be sure to name your output file something that is recognizable as your work, and unlikely to collide with the names of others. 
   * Include logging that lets the executor know how many of the records failed to join, and include a join error threshold above which the script will error out. 

2. *Transformation challenge* - write a script which anonymises the SR file, but preserves the following resolutions (You may use H3 indexes or lat/lon coordinates for your spatial data):
   * location accuracy to within approximately 500m 
   * temporal accuracy to within 6 hours
   * scrubs any columns which may contain personally identifiable information.
 
Your code should be well formatted according to generally accepted style guides and include whatever is necessary for a team-mate unfamiliar with it to maintain it.

## Contact

You can contact riaz.arbi, gordon.inggs and/or colinscott.anthony @ capetown.gov.za
