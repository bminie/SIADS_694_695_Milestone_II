# SIADS_694_695_Milestone_II
The goal of this project is to use supervised learning to test models for cell type prediction and unsupervised learning to test models for clustering of single cell RNAseq data.

The data set contains approximately 50,000 cells with both the raw transcript counts as well as data generated using the Seurat standard pre-processing workflow (https://satijalab.org/seurat/articles/pbmc3k_tutorial.html). In additional to the previously described information, our data set also contains cell type annotations that were provided by a team of experts in the field and will be used through the course of our work. This data set does not contain any patient/donor information.

## Data Merging
Due to the original large file size of the data, the file was split and needs to be reassembled before use.

To reassemble the file, run cat xa{a..c} > cells.h5ad

## Generating Train and Test Data Sets
To generate the training and test data sets, you can run the notebook Generate_multiple_pca.ipynb.

This notebook will using multiple iterations of PCA to generate a handful of training and test sets. Included in this train-test set generation is a step to use the PC's calculated during the Seurat pre-processing and create training and test sets from them. All the other train-test sets will be generated using ScanPy standard pre-processing steps with only the number of principal components changing each time.

## Supervised Learning
The goal of the supervised learning portion of the project is to test different supervised learning algorithms for cell type label prediction.

The following supervised learning classifiers/algorithms will be tested: Dummy classifiers, K-Nearest Neighbors, Support Vector Machines, Decision Tree, Gradient-Boosted Decision Tree, Naive-Bayes Classifier, Random Forest, and a Neural Network.

The input into the different classifiers will be the train-test sets that were generated as part of the Generating Train and Test Data Sets step. For each model, the different data sets generated using the varying number of principal components will be tested. Precision, recall, and f1-score will be calculated and plotted for each model. A summary dataframe that contains all the information will also be generated so it can be used for further analysis if desired.

To run the models, you can run the notebook Supervised_Learning.ipynb

## Unsupervised Learning
TBD
