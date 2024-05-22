### Project Title

Vaishnavi Nagesh

#### Executive summary
This capstone project investigates Machine Learning techniques to enhance the accuracy of functional prrediction of proteins. Proteins are responsible for many activities in our tissues, organs, and bodies and they also play a central role in the structure and function of cells. Proteins are large molecules composed of 20 types of building-blocks known as amino acids. This amino-acid sequence determines the 3D structure and conformational dynamics of the protein, and that, in turn, determines its biological function. Due to ongoing genome sequencing projects, we are inundated with large amounts of genomic sequence data from thousands of species, which informs us of the amino-acid sequence data of proteins for which these genes code. The accurate assignment of biological function to the protein is key to understanding life at the molecular level. The Gene Ontology (GO) is a concept hierarchy that describes the biological function of genes and gene products at different levels of abstraction (Ashburner et al., 2000). It is a good model to describe the multi-faceted nature of protein function.

I have used Neural networks, multi output logistic regression to assess the function of the proteins.


#### Rationale

Since this is a multilable problem, neural networks was a no-brainer choice. However, I was interested in comparing the classi ML models too, which is where MultiOutput Logistic Regreession comes along.
While no hyper paramter tuning was employed for NNs, Grid Search was done to estimate the best hyper parameters for Logistic Regression.

#### Research Question

Functional Prediction of Proteins.

#### Data Sources

https://www.kaggle.com/competitions/cafa-5-protein-function-prediction/data

#### Methodology

Exploratory Data Analysis:

1. To understand the distribution labels.
2. To understand which GO terms are most frequently occuring.
3. To subsample the GO terms to assign such that models do not run too long.

Neural Networks:
1. Using Dense Neural Network.
2. Using Adam Optimizer

MultiOutput Logistic Regression:
1. GridCV was used for hyper parameter tuning



#### Results

NN gives me 98% accuracy. Jury is still out for Logistic Regression since it is still running

#### Next steps

The real meaning would be if we can identify the function of the protein in terms of its weights in Biological Process, Cellular Process and Molecular Function. Having that information wil give us a lot more usable information of the protein.

#### Outline of project

- https://github.com/VNagesh-Bio/CAFA5/blob/master/EDA_Capsotne.ipynb
- https://github.com/VNagesh-Bio/CAFA5/blob/master/v-pc-ml-aicapstone-submission.ipynb

##### Contact and Further Information
vaishnavi.nagesh@gmail.com
