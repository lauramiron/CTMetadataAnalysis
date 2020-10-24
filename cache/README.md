## Readme.md

To ease analysis, this code scrapes values from raw XML CT.gov records, places the results in pandas dataframes, and stores those dataframes in this folder as pickle (or csv) files.

The "scrape" step happens in Validation.ipynb and only needs to be run once.  Analyses in different notebooks will access the contents of these dataframes rather than parse the raw XML files again.

Recreating all of the dataframes can be time-consuming, on the order of several hours to generate them all.  To speed up usage of the code, these pickle files can also be downloaded from our figshare and placed in this folder.

The necessary files are:
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
