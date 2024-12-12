# NarleskiThompson_ENV872_EDA_FinalProject
# Fish Tissue Contamination Trends in the Great Lakes
General Notes: This is our final project repository for Environmental Data Exploration. Our project will be focusing on fish tissue contamination in the Great Lakes. 

## Summary

The Environmental Protection Agency has conducted multiple studies over the past 15 years assessing the coastal conditions of marine and the Great Lakes shores. The purpose of these National Coastal Condition Assessments (NCCA) is to observe and determine what environmental or anthropogenic changes may affect the water quality of these water bodies. The NCCA is conducted every 5 years, with studies starting from 2010.  
A key part of the NCCA is the fish tissue contamination study the EPA conducts of fish species that recreational fishers catch in the Great Lakes. Samples are taken and analyzed for mercury, PFAs (per- & polyfluoroalkl substances), PCB (polychlorinated biphenyls) Congeners & Aroclors, and Omega-3 & Omega-6 fatty acids. The EPA uses the results from these studies to evaluate the water quality of the Great Lakes and more specifically, determine the health impacts humans may have from consuming fish caught in the Great Lakes.  
As investigators, we aim to investigate how fish tissue contamination varies (1) between lakes, (2) within species over time, and (3) between different aquatic niches. 

## Investigators
Jaclyn Narleski, Master of Environmental Management student at the Nicholas School of Environment, Duke University  
Contact: jaclyn.narleski@duke.edu  
Victoria Thompson, Master of Environmental Management & Forestry student at the Nicholas School of Environment, Duke University  
Contact: victoria.thompson@duke.edu

## Keywords
Fish tissue, contamination, Great Lakes, bioaccumulation

## Database Information
All data in the repository was sourced from https://www.epa.gov/choose-fish-and-shellfish-wisely/national-coastal-condition-assessment-great-lakes-human-health#:~:text=The%20EPA%20conducts%20fish%20tissue,the%20data%20to%20the%20EPA. All data is digitized from field and lab samples from the NCCA. All data was last accessed 12-10-2024.

- 2010 Data:
  - Mercury: https://www.epa.gov/system/files/documents/2021-10/glhhffts-mercury-data-2015.xlsx
  - PFAs: https://www.epa.gov/system/files/documents/2021-10/glhhffts-pfas-data-2015.xlsx
  - PCBs: https://www.epa.gov/system/files/documents/2021-10/glhhffts-pcb-data-2015.xlsx
  - Fatty Acids: https://www.epa.gov/system/files/documents/2021-10/glhhffts-fatty-acids-data-2015.xlsx
- 2015 Data:
  - Mercury: https://www.epa.gov/system/files/documents/2021-10/glhhffts-mercury-data-2015.xlsx
  - PFAs: https://www.epa.gov/system/files/documents/2021-10/glhhffts-pfas-data-2015.xlsx
  - PCBs: https://www.epa.gov/system/files/documents/2021-10/glhhffts-pcb-data-2015.xlsx
  - Fatty Acids: https://www.epa.gov/system/files/documents/2021-10/glhhffts-fatty-acids-data-2015.xlsx
- 2020 Data: https://www.epa.gov/choose-fish-and-shellfish-wisely/2020-great-lakes-human-health-fish-fillet-tissue-study
  - Mercury: https://www.epa.gov/system/files/documents/2024-04/glhhffts-mercury-data-2020.xlsx
  - PFAs: https://www.epa.gov/system/files/documents/2024-04/glhhffts-pfas-data-2020.xlsx
  - PCBs:https://www.epa.gov/system/files/documents/2024-04/glhhffts-pcb-congener-data-2020.xlsx
  - Fatty Acids: https://www.epa.gov/system/files/documents/2024-04/glhhffts-fatty-acid-data-2020.xlsx
 
Some supplementary data was pulled in from the 2020 NCCA Quality Assurance Report (Appendix A). in order to map the sites: chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://www.epa.gov/system/files/documents/2024-04/glhhffts-qa-fish-sample-preparation-2020.pdf. The data was scraped from the pdf into an excel sheet and input as a .csv file.

## Folder structure, file formats, and naming conventions
Folders include "RawData" and "ProcessedData". Data files are all downloaded/processed into csv format. All Raw data is named Year_Contaminant_Raw.csv. All Processed data is named Year_Contaminant_Processed.csv. 

The exception to this convention is the supplemental spatial data, which is called 2020sitelocations.csv and was extracted manually from the 2020 NCCA Quality Assurance Report (see above). The spatial dataset for counties is named cb_2018_us_county_20m.(file type), with the various spatial file types required for mapping. These are all within the Raw Data file, as they were not changed from their imported values. 

## Metadata
For the raw data files from NCCA, the columns are as follows: 
- EPA Region: The EPA Region in which the sample was collected
- State: 2-letter abbreviation for the state in which the sample was collected
- Lake: The Great Lake the sample is from
- Site ID: “NGL” + site selection year + state + 4-digit site location
- EPA Sample: ID	6-digit code assigned by the EPA
- Scientific.Name:	Taxonomic name of fish sampled
- Common.Name: Common name of fish sampled
- Family:	Taxonomic family of fish sampled
- Tissue Type: The type of fish tissue used for analysis; we use only fillet data
- % Lipids: The lipid content of the sample, measured independently of the chemical analysis
- Method: EPA-standardized method of chemical analysis
- Analyte: The chemical of interest in each dataset
- Amount: Amount of chemical detected in the sample
- Unit.1:	The original unit the chemical was measured in ("ng/g (nanograms per gram)" for Mercury, PFA, PCB. "mg/g (milligrams per gram)" for Fatty Acids) 
- Unit.2:	The amount of chemical converted to common units. Only for some contaminants ("ppb (parts per billion)" for Mercury, PFA, PCB. "ug/g (micrograms per gram)" for Fatty Acids)

    
For the processed data files from NCCA, the columns are as follows: 
- State:	2-letter abbreviation for the state in which the sample was collected
- Lake:	The Great Lake the sample is from
- Scientific.Name:	Taxonomic name of fish sampled
- Common.Name: Common name of fish sampled
- Family:	Taxonomic family of fish sampled
- Niche:	Codified ecological niche of the fish sampled; “BD” is “Benthic-Demersal”, “P” is “Pelagic”
- Method:	EPA-standardized method of chemical analysis
- Analyte:	The chemical of interest in each dataset
- Amount:	Amount of chemical detected in the sample
- Unit.1:	The original unit the chemical was measured in

For the site mapping data, the columns are as follows:
- LAKE: The Great Lake the sample is from
- STATE: 2-letter abbreviation for the state in which the sample was collected
- SITE ID: “NGL” + site selection year + state + 4-digit site location
- LATITUDE: Latitude of sampling site
- LONGITUDE: Longitude of sampling site

## Scripts and code
NarleskiThompson_ENV872_EDA_FinalProject.Rmd - Script containing the entirety of project setup and analysis. Includes data input, wrangling, processing, and analysis.
