# Predicting-the-activity-of-drugs-on-COVID-protein
---
Creating a new drug for COVID is very expensive and take a lot a lot of time to develop and check its safety so an easier and faster way to find treatment for COVID is finding a drug that is used for other indication that has activity on the viruses and then investigate it more to see this activity is antiviral and the safety and other dimensions of developing and testing a drug. We can create a ML model that predicts the if a molecule is active against COVID (proteins or other parts). Then use it to scan a massive library of drugs stored in drugs data banks and we will get candidates for farther research and investigation.
---

# The project steps:

## Importing and installing libraries
Installed chembl client and imported the required libraries for analysis like pandas, numpy, matplotlib, seaborn

## Cleaning the data 
I explored the data and cleaned it by:
- Extracting the rows that has standard type IC50
- Changing columns type to the appropriate type
- Some molecules had multiple rows with different values so I aggregated them and calculated their mean
- Categorized the standard values into inactive, intermediate, and active

## Feature engineering

I created new feature form the data I have by:
- Making a mole columns that has the molecular representation of the molecules
- Calculating lipinski descriptors from the smiles (representation of the molecular structure)
- I made a new data frame that has the name and structure of the molecules and the calculated descriptors as well as the activity class
- Added the log of the mean standard values because those values were skewed

## Statistical analysis
**Is the active drugs population differ from the inactive in regard to the descriptors in the dataframe?**


**After analysis conclusion**:  Using mann whitney u test, it appears that the population does't differ in the featured except for the PIC50 and that clearly because the bio-activity classes were made using cut off values from the IC50 values.

**So I needed to calculate more descriptors**

## Calculating More descriptors

I used padelpy library to calculate some more descriptors from the smile of every molecule
 
 ## Machine learning model creation

### preprocessing:

* Extracted the class column to be the target (y) and the rest of the column will be the predictors (x)
* Removed unwanted columns 
* Converted the columns to numeric data so it could be modeled 
* Removed PIC50 column as the target Y is calculated from it and that would lead to data leakage
* Removed columns with low variance in x as probably they won't be of any help
* Splitted the data to train and test sets and stratified them using y to insure that every split contains the same percentages of the different classes
* Normalized the data using standard scaler

### Training and testing

I created many ML algorithms and fine tune every model using grid search technique to find the best hyperparameter then compare their performance

## End notes
Those models could be used to scan drugs databases and library to find a drug that would be categorized as active drug against the chosen protein. those drugs would be interesting candidate for investigation for finding new use for already made drugs in covid as that would be much faster and easier than creating and testing new molecules. this method could be used for different proteins of covid virus by simply changing the chosen protein in scraping data section

## Limitations
I could't create more complex models because I do't have the resources to do so. This is just testing of the idea but those models are not ready for production as It needs more data to train on and more resources so I could try more algorithms and finer tuning of the hyperparameter
