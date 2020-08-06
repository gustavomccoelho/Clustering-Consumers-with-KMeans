## Business problem definition
The main purpose of this small project is to calculate the mean electric power consumption per customer segment. 

## Dataset
The dataset is provided by UCI.

## Scrip ste-by-step
The dataset is loaded in a Pandas DataFrame. To enhance performance, the dataset actually used is 1% of the original, which is too large be handled by a standard computer. Ideally, this scrip should run in a cluster, such as Spark, so the entire dataset can be utilized. 

Once we have the dataset sample in place, we first handle the NA values. Following, we scale the dataset, to be best handled by the cluster algorithm, which is choosen to be K-Means. 

To decide the proper number of cluster, the Elbow Method is used, as shown in the picture below:

![elbow](/pictures/elbow.png)

The choosen number of clusters is 4.

After the model is in place, PCA is used to reduce the dimensions and plot the results, as bellow:

![clusters](/pictures/clusters.png)

The mean consumption is then calculated per cluster, providing the final result.

