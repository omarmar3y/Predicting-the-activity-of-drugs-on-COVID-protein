# Predicting-the-activity-of-drugs-on-COVID-protein
---
Creating a new drug for COVID is very expensive and take a lot a lot of time to develop and check its safety so anan easier and faster way to find treatment for COVID is finding a drug that is used for other indication that has activity on the virues and then investigate it more to see this activity is antiviral and the safety and other dimensions of developing and testing a drug so we can create a ML model that predicts the if a molecule is active against COVID (proteins or other parts) then use it to scan a massive library of drugs stored in drugs data banks and we will get candidates for farther research and investigation
---
* Using chembl library to scrape protein bank from the internet 
* search for COVID discovered proteins choosing one 
* search for all the drugs that been tested their activity of this protein 
* explore and clean the data 
* calculate some descriptors to use it as features of predictive model 
* create many models then chose the best models (with highest scores) 
* use grid search to fine tune the hyperparameters 
* analyize the performance of the chosen model
