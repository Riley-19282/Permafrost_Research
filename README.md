README

**About:** This repository holds all relevant code and data collected from permafrost incubation studies conducted August 2023 - May 2025. 
This is an overview of the script functions and where relevant data is listed. 
Each data file also has an individual readme sheet which provides more detailed information on data naming/ formatting.


**Scripts:** 

_Standardized GasBench Data Processing_ - https://github.com/Riley-19282/Permafrost_Research/blob/main/Standardized_GasBench_data_processing.ipynb - 
This script is to process data collected on a ThermoFisher GasBench II GC-IRMS using the methane method. The methane method separates the CO2 and CH4 in one gas sample and measures the amount 
and d13C values of both gases. 
The raw xlsx file from the GasBench can be directly uploaded into this script. Then the following corrections are preformed: 1) blank correcting both carbon amounts and 
d13C values, 2) create a calibration curve of known CO2 and CH4 gas standards to find the amount of CO2 and CH4 in samples, and 3) create a calibration curve of known isotope standards
to correct the measured d13C values of the samples. The corrected data (CO2, CH4, d13C-CO2, and d13C-CH4) can then be exported. Important notes: filtering is done using specific naming
conventions and is case sensitive so ensure that raw data file uploaded adheres to the naming convention. Filtering is also done using peak number (ie peak 3=CH4 peak, peak 4=CO2 peak) so ensure
uploaded data adheres to peak numbering system. Lastly, the script has pre-built functions to drop outlier data, but the user should ensure the drop code is commented out first and only used as needed.

_Final Cumulative Incubation Data_ - https://github.com/Riley-19282/Permafrost_Research/blob/main/Final_Cumulative_incubation_data.ipynb - 
This script is to combine and process all collected incubation data. Note any raw data collected should first be processed using _Standardized GasBench Data Processing_ then added to the 
Cumulative incubation data file (https://github.com/Riley-19282/Permafrost_Research/blob/main/Incubation%20Data/Cumulative%20incubation%20data.xlsx), which can then be uploaded and manipulated using this script.
This script contains all the necessary code to scale up measured data and complete other corrections/ normalizations. This script also contains code to preform linear regressions and t-tests. 
Finally, this script also contains many graphs/ data visualizations and code to export data. 

_Final Box Model_ - https://github.com/Riley-19282/Permafrost_Research/blob/main/Final_box_model.ipynb - 
 This script first generates a simple, mass-only 2-pool box model. The model is then expanded to include d13C values in the 2-pool box model. 
Then, using uploaded initial incubation data, this script models the CO2 and d13C-CO2 values of the incubations through time. All model parameters are listed as unique variables
which can be manipulated. 

_Smith Lake Soil Temperatures_ - https://github.com/Riley-19282/Permafrost_Research/blob/main/Smith_Lake_soil_temps.ipynb - 
This script can take uploaded soil temperature probe data (recorded hourly) and reformats the data for monthly, seasonal, and yearly averages. The data is then plotted on a depth vs 
temperature plot and uses a color gradient to denote the year. Important physical characteristics such as the active layer, talik layer, and permafrost table are outlined.

**Data Files:**

**_Incubation Data_** -

https://github.com/Riley-19282/Permafrost_Research/blob/main/Incubation%20Data/Cumulative%20incubation%20data.xlsx 
This file is all incubation data that has been processed using _Standardized GasBench Data Processing_ only. This file is then uploaded to the _Final Cumulative Incubation Data_
script for further processing. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/Incubation%20Data/processed%20cumulative%20incubation%20data.xlsx 
This file includes raw incubation data, unaveraged incubation data, and averaged incubation data. This file contains a few selected dataframes from within the _Final Cumulative Incubation Data_
script that have been exported. This includes data such as linear regression production rates, CO2 and CH4 over time (per gram dry weight, per mg DOC, per gram TOC, etc.), standard errors, final d13C values, etc. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/Incubation%20Data/Production%20rates.xlsx 
This file includes all production rates (slopes), y-intercepts, and r squared values from linear regressions (weight to grams dry weight). Linear regression slopes weighted per g TOC and mg DOC 
are also listed. Lastly, this file also includes rate constants (k) used in the final box model. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/Incubation%20Data/core%20characteristics.xlsx 
This file includes all relevant core characteristics of incubation material. This includes organic carbon (TOC and DOC), nitrogen content, water content, pH, sample depth, d13C TOC, d15N, and grain density. 

**_Box Model Data Files_** - These files include data exported from _Final Cumulative Incubation Data_ script and are necessary to initiate the final box model. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/box%20model%20data%20files/C-CO2%20final.xlsx 
This file includes the CO2 data and standard error over time. Note CO2 data is in grams of carbon from CO2. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/box%20model%20data%20files/calcite%20corr%20d13C%20CO2.xlsx 
This file includes the final calcite corrected d13C-CO2 values and standard error over time. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/box%20model%20data%20files/corrected%20cumulative%20CO2%20data.xlsx 
This file contains the initial organic carbon (i.e. the grams of total organic carbon present). Note this comes from TOC measurement not DOC. 

https://github.com/Riley-19282/Permafrost_Research/blob/main/box%20model%20data%20files/d13C%20TOC.xlsx 
This file contains the 'parent d13C' which is the measured TOC d13C value for each sample. 
