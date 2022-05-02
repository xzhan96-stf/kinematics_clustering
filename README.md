## Piecewise multivariate linearity between kinematics features and cumulative strain damage measure (CSDM) across different types of head impacts
## Abstract
In the previous study, we found that the relationship between brain strain and kinematics features cannot be described by a generalized linear model across different types of head impacts. Therefore, we hypothesized that a piecewise linear relationship existed between brain strain and kinematics features across different types of head impacts. To validate this hypothesis, we applied the K-means clustering to partition 3,161 impacts from various sources including simulation, college football, mixed martial arts, and car crashes, and found piecewise multivariate linearity between the cumulative strain damage (CSDM) and head kinematics features. Compared with the linear regression models without partition and the partition according to the types of head impacts, K-means-based data-driven partition showed significantly higher CSDM regression accuracy, which suggested the presence of piecewise multivariate linearity across types of head impacts. Additionally, we compared the piecewise linearity with the partitions based on individual feature used in clustering, and found that the partition with maximum angular acceleration magnitude at 4706 rad/s^2 led to highest piecewise linearity.

# Datasets
Directory: ./Data/X 
Data Format: .mat
Description: The kinematics features (352-dimensional) extracted from the kinematics measurements and the BIC (15-dimensional) for four different datasets. (HM: HM1, HM2, 2130 impacts; CF: CF1, CF2, 302 impacts; MMA: MMA1, MMA2, 457 impacts; NASCAR: 272 impacts)

Directory: ./Data/Y
Data Format: .npy
Description: The response variable (CSDM15) for four different datasets. (HM: 2130 impacts; CF: 302 impacts; MMA: 457 impacts; NASCAR: 272 impacts)

# Code
Directory: ./Code
1) baseline_function.py: functions and code used for the baseline modeling: load the data, set up the hyperparameters, perform cross-validation, model evaluation on the test set;
2) class_data.ppy: the required data type and functions used to load the datasets, store the data, partition the training and test dataset, perform bootstrapping;
3) classification_regression_model.py: the definition of the class of classificaiton and regression model, involving functions used to make prediction, make predictions of the domain of a new sample, perform domain-specific regression for the new sample;
4) classify_N_regression.py: the file perform the classification and regression task (benchmark No. 2). Load data, partition train/test, model the classifier, perform class-specific regression;
5) clustering.py: the file contains the code for building clustering models, evluate the clustering results with Silhouette score, Davies bouldin score and Calinski Harabasz score, get the robust clustering labels (get the mean cluster index), evaluate the clustering model robustness. It should be mentioned that most of the functions are not used for the results reported in the manuscript;
6) clustering_n_regression.py: the flie performs the clustering on the impacts and the domain-specific regression after the impacts got clustered into two domains;
7) model_constant.py: the files stores the constants/model hyperparameter combinations for the regression modeling;
8) visualization.py: this files contain the necessary functions for plotting and data visualization including the plotting of boxplots;
9) result_process.py: this file processes the output of the previous code output by extracting the numerical results of the CSDM estimation, perform result visualization via boxplot drawing and the multiple statistical tests.

For more questions, please contact the developers via email:
Xianghao Zhan
xzhan96@stanford.edu
Yiheng Li
yyhhli@stanford.edu
