# 3D-printing
This project presents a novel approach to predict the quality of 3D-printed objects using multiple measurement data sources. The result shows feature extraction from high-dimensional image data as a promising technique for efficient and 
automated quality inspection. 
The package includes raw R program and all collected data.

## How to read final.Rmd 
The final.Rmd notebook includes several blocks of codes. The functionality of each code will be explained below.

### 3D scanner
Import 20 3D scanner image data matrices from "3D_scanner" folder. Split the 20 samples into training and testing set (14:6).
Implement principal component analysis on both training and testing set and extract first four principal components.

### roughness
Import roughness data from "roughness3" folder. Take average of two roughness data from 20 samples. Split roughness data into same training and testing 
set as data matrices.

### profile deviation
Import profile deviation from "profile_quality.csv" file. Split profile deviation data into same training and testing 
set as data matrices.

### preliminary regression
Create data frame consists of predictors(PCs, fill, thickness and speed) for preliminary regression.

### profile
Train profile deviation model using training set and test the performance using testing set. Compute MSPE(mean square prediction error).

### roughness
Train roughness model using training set and test the performance using testing set. Compute MSPE(mean square prediction error).

### Clustering
Cluster the training sample into three clusters: good, uncertain and bad. Find thresholds for those three clusters and classifer the test result
from the thresholds. Find "uncertain" test samples.

### high resolution
Import wide-area 3D measurement data matrices from "matrix" folder. 

### UMPCA
Implement uncorrelated multilinear principal component analysis on 
both training and testing set and extract first four principal components.

### refined regression
Create data frame consists of predictors(MPCs, fill, thickness and speed) for refined multi linear regression.

### profile2
Train refined profile deviation model using training set and test the performance using "uncertain" testing set. Compute MSPE(mean square prediction error).

### roughness2
Train refined roughness model using training set and test the performance using "uncertain" testing set. Compute MSPE(mean square prediction error).

