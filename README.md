# Côte d'Ivoire Biomass Density Estimation Project 
## A Comparative Study of Random Forests and CNN in Estimating Biomass and the Relative Importance of Spectral Bands, Cloud Cover, Latitude, and Longitude in the Modeling Process

This repository contains work for the final project for IDS 705. This project’s goal is to to improve the efficiency of biomass estimation using machine learning techniques in areas experiencing deforestation. Biomass has traditionally been measured manually by field experts, which is costly, time-consuming, and difficult to scale. This project explores remote sensing techniques using satellite images. Specifically, this analysis compares the performance of Random Forest models against ResNet Convolution Neural Networks in predicting Above Ground Biomass (AGB) of cocoa plantations in Côte d'Ivoire. 

The results of this project suggests that these models are ineffective at predicting biomass from Sentinel-2 satellite imagery. While other studies have successfully implemented both of these methods for predicting biomass, the referenced work appears limited to higher resolution imagery (i.e. UAV and high resolution imagery).  Additionally, this analysis compares the importance of the image data (i.e., spectral bands, cloud cover, and location), which suggests that the Infrared and vegetation red wavelengths are most important in predicting biomass.  However, due to the inconsistency in feature importance across models, and multicollinearity between bands, this analysis cannot be considered a causal effect. 

# Setup Instructions
Python version: 3.10 and above
Packages: run `make install` in terminal 

# Run the Files
* Under the PreProcessing directory, you can find code and instruction on how to get and pre-process the data: 
    * Run `python data_load.py` in terminal

* Under the Models directory, you can find code for how to fit the Random Forest and ResNet Models. Below is our modeling process map:
<img width="931" alt="process_map" src="https://user-images.githubusercontent.com/105904149/232633385-61601c68-9b3b-44ee-ab6b-cad6ee6b17cf.png">

    * `random_forest.ipynb`: outlines the model fitting and experiments of the Random Forest model and their results. 
    * `CNN.ipynb`: outlines the model fitting and experiments of the ResNet 50 and ResNet 32 models and their results.

# Best Results
|             |  Fine-Tuned Random Forest  | ResNet-32 Model Trained on All Normalized Features |
|-------------|----------------------------|----------------------------------------------------|
| RMSE        | 64.63                      | 60.27                                              |
| R-Sqaured   | 1.68%                      | 14.49%                                             |

