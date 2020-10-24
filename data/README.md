## Readme.md

Notebooks expect two data files to be copied into this folder from our figshare (https://figshare.com/articles/dataset/Data_from_Obstacles_to_the_Reuse_of_Study_Metadata_in_ClinicalTrials_gov_/12743939):
* condition_matches.csv
* intervention_matches.csv

These files are too large to be stored in github.  They contain the results of using java code from (https://github.com/metadatacenter/metadata-analysis-tools) to query the BioPortal API for ontology terms that are exact matches for values from the 'condition' and 'intervention' fields in CT.gov records.
