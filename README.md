### Project Title

Functional Prediction of Proteins - CAFA5 Challenge

#### Executive summary
This capstone project investigates Machine Learning techniques to enhance the accuracy of functional prrediction of proteins. Proteins are responsible for many activities in our tissues, organs, and bodies and they also play a central role in the structure and function of cells. Proteins are large molecules composed of 20 types of building-blocks known as amino acids. This amino-acid sequence determines the 3D structure and conformational dynamics of the protein, and that, in turn, determines its biological function. Due to ongoing genome sequencing projects, we are inundated with large amounts of genomic sequence data from thousands of species, which informs us of the amino-acid sequence data of proteins for which these genes code. The accurate assignment of biological function to the protein is key to understanding life at the molecular level. The Gene Ontology (GO) is a concept hierarchy that describes the biological function of genes and gene products at different levels of abstraction (Ashburner et al., 2000). It is a good model to describe the multi-faceted nature of protein function.

I have used Neural networks(base line as provided in CAFA challenge), multi output logistic regression to assess the function of the proteins.


#### Rationale

Since this is a multilable problem, neural networks was a no-brainer choice. However, I was interested in comparing the classi ML models too, which is where MultiOutput Logistic Regreession comes along.
While no hyper paramter tuning was employed for NNs, Grid Search was done to estimate the best hyper parameters for Logistic Regression.

#### Research Question

Functional Prediction of Proteins.

#### Data Sources

https://www.kaggle.com/competitions/cafa-5-protein-function-prediction/data

#### Methodology

Exploratory Data Analysis:

1. Reporting the distribution of labels.
2. To understand which GO terms are most frequently occuring.
3. Obtaining protein embeddings to meaningfully use the sequence data in classification. Biopython library was used in loading sequences and protein embeddings created by Sergei Fironov using the Rost Lab's T5 protein language model was utilized.
4. To subsample the GO terms to assign such that models do not run too long - Subssampling of labels was done per 'aspect' term such that the distribution of the aspect was maintained in the terms to the best possible extent

Classification Methods Used:

1. Neural Networks
2. MultiOutput Logistic Regression
3. MultiOutput Ridge Classifier
4. MultiOutput Random Forest Classifier

Grid search and hyperparameter tuning was done on the first 1000 - 2000 samples. The best model identified was then trained on the complete training set. This was done after I observed that grid searching on such a large dataset was taking more than a day on laptop.


#### Results

##### Exploratory Anayses
Number of Unique Protein IDs: 142246
Number of GO terms shared by the proteins: 31466
Number of Aspects or Functional Classes being Represented: 3
Each protein is represented by many GO terms, in turn having multiple aspects to its functionality

![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/0b780c89-e5ac-4d4d-ad99-e7daf251dcbc)

Among the GO Terms, the following aspects of the proteins are distributed as shown in the pie-chart

![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/19ddea38-35ef-4217-8c13-2e48484312f7)

Based on the ratio of the aspects, the most frequent GO terms in each category were chosen such that we down sample the labels to be predicted while maintaining the distribution of the aspect to the closest possible extent.

![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/b06afc19-1495-474f-82a3-7da7d25a0984)

In the Kaggle Challenge, the baseline model was that of Neural Networks which acheived 98% accuracy.

![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/c45e80ac-9959-4f87-bc49-9f0e777e0214)    ![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/360a7f64-1d6c-4579-a005-cfdf25a3ee2d)






##### Confusion Matrics of Three Classifiers - On first 15 lables

Logistic Regression Classifier:
![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/f9ff0fac-2ac0-4837-ba61-025b8c4ecacc)



Ridge Classifier:
![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/abfa8487-dbf6-48d1-b001-cb9c368c5480)



Random Forest Classifier:
![image](https://github.com/VNagesh-Bio/CAFA5/assets/3857429/c0dacaaa-7423-4c85-9b0a-9299e3a719d6)



GO:0001850 always seems to have high false negative rate. At some point it will become necessary to diagnose why a certain label always gets misclassified more number of times than others.

##### Precision Recall and F1 Scores Among the Classifiers:

| Classifier                                          | Accuracy   | Precision | Recall | F1 Score |
| --------------------------------------------------- | ---------- | --------- | ------ | -------- |
| Neural Nets                                         | 98         |           |        |          |
| Logistics Regression                                | 83.22      | 0.64      | 0.44   | 0.47     |
| Ridge Regression Classifier                         | 83.14      | 0.66      | 0.42   | 0.44     |
| Random Forest Classifier                            | 81.28      | 0.52      | 0.26   | 0.24     |


Overall Neural Nets definitelly appears to model and predict the data better than machine learning models. However, it must be noted that, it took a lot longer to train machine learning models. This was a bottle neck in grid searching and tuning the hyper paramters. Among the three classifiers, if I were to have resource and re-train an ML model, I would choose Logistic Regression.

#### Next steps

The real meaning would be if we can identify the function of the protein in terms of its weights in Biological Process, Cellular Process and Molecular Function. Having that information wil give us a lot more usable information of the protein.

#### Outline of project

- https://github.com/VNagesh-Bio/CAFA5/blob/master/EDA_Capsotne.ipynb
- https://github.com/VNagesh-Bio/CAFA5/blob/master/v-pc-ml-aicapstone-submission.ipynb

##### Contact and Further Information
vaishnavi.nagesh@gmail.com
