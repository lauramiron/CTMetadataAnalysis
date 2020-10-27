# CTMetadataAnalysis
Code and data files for "Obstacles to the Reuse of Study Metadata in ClinicalTrials.gov"

## Installation Instructions
The file requirements.txt defines a python3 virtual environment that can be used to run these notebooks.

#### Install pip and virtualenv
On macOS and Linux:

    $ python3 -m pip install --user --upgrade pip
    $ python3 -m pip install --user virtualenv

On Windows:

    $ py -m pip install --upgrade pip
    $ py -m pip install --user virtualenv

#### Create a virtual environment
At a location outside of the project folder:

On macOS and Linux:

    $ python3 -m venv env
    $ source env/bin/activate

On Windows:

    $ py -m venv env
    $ .\env\Scripts\activate
  
#### Install the requirements:

    $ cd CTMetadataAnalysis
    $ pip install -r requirements.txt
  
#### Install a new ipython kernel using this environment:

  $ python -m ipykernel install --user --name metadata
  
Now, you may start jupyter notebook, and select the kernel called "metadata" for all notebooks.
  
  
## Repository Structure
### Main Code
The four jupyter notebooks Validation.ipynb, Completeness.ipynb, OntologyTerms.ipynb, and Eligibility.ipynb together reproduce the results for the manuscript "Obstacles to the Reuse of Study Metadata in ClinicalTrials.gov" (https://www.biorxiv.org/content/10.1101/850578v3.full).  To reproduce results from the manuscript, the intended order to run the notebooks is:
1. Validation.ipynb - Check that ClinicalTrials.gov records validate against the expected schema (public.XSD)
2. Completeness.ipynb - Check that ClinicalTrials.gov records contain values for required fields
3. OntologyTerms.ipynb - Check whether user-provided values for the "condition" and "intervention" fields are drawn from biomedical ontologies such as MeSH and SNOMED
4. EligibilityCriteria.ipynb - Check whether eligibility criteria adhere to the expected format

### Data Files
Data files are available at (https://figshare.com/articles/dataset/Data_from_Obstacles_to_the_Reuse_of_Study_Metadata_in_ClinicalTrials_gov_/12743939).
* AllPublicXML.zip must be downloaded.  Unzip file to an appropriate location (~7GB) and update the path in the top of notebook files, where indicated by comments
* cache.zip may optionally be downloaded from the figshare and unzipped and placed inside the CTMetadataAnalysis, replacing the current cache/ folder.  This enables skipping the "scrape XML" steps of the code, which can take several hours, and running only the analysis portions of the code.  The complete list of files that 

If cache.zip is not downloaded from the figshare, the notebooks will scrape values from the XML files in AllPublicXML into pandas dataframes.  These dataframes will be saved as pickle (or csv) files to the cache/ folder.  The total list of files that will either be generated or downloaded from the figshare is:
* allocation.p
* applicable.p
* arm_group_type.p
* arm_info.p
* condition.csv
* contacts.p
* facility.p
* intervention_model.p
* intervention.csv
* investigators.p
* masking.p
* observational_model.p
* overall_contact.p
* primary_outcome.p
* primary_purpose.p
* single_required_fields.p
* study_types.p
* time_perspective.p

### Results
Final results files will be placed in the results/ folder by the python notebooks. The complete list of expected results files to be generated is:
* completeness.csv
* industry_completeness_after_FR.csv
* industry_completeness_before_FR.csv
* industry_completeness.csv
* location_completeness_after.csv
* location_completeness_before.csv
* location_completeness.csv
* xml_val_results.csv
* figure1.png
* figure2.eps
* figure3.eps
* figure4.eps
