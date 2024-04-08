# Customer group segmentation (ML)
The objective of this project is to clusterize mall customers into 'n' clusters using K-Means ML algorithm and derive valuble insights into their annual income and spending scores.<br><br>
## Tools and technology
1. Python
2. Google CoLab
3. Scikit-learn
4. K-Means
5. Pandas
6. Numpy
7. Matplotlib
8. Seaborn<br><br>
## Process
- Dowload the Mall_Customers.csv file and the **Customer_segmentation_ML.ipynb** file from this repository
- Open [Google Colab](https://colab.research.google.com)
- Upload the downloaded python file
- Navigate to the notebook that was uploaded on Colab
- Click on file icon on the left pane and upload the dataset
- Run the notebook<br><br>
## Analysis
```
# plotting an elbow graph to find which cluster has minimum wcss value
sns.set()
plt.plot(range(1,11), wcss)
plt.title('The elbow point graph')
plt.xlabel('Number of clusters')
plt.ylabel('WCSS')
plt.show()
````
<img width="607" alt="Screenshot 2024-04-08 at 3 27 29 AM" src="https://github.com/rohitpaul1998/Customer_group_segmentation_ML/assets/113409553/08d46f43-cc59-434c-9199-9529a65a896c"><br><br>
- The optimum number of clusters will be 5 since there is no significant drop after 5th cluster on the x-axis.<br><br>
## Cluster Visualization
```
# plotting all the clusters and their centroids
plt.figure(figsize=(8,8))
plt.scatter(X[Y==0,0], X[Y==0,1], s=50, c='green', label='Cluster 1')
plt.scatter(X[Y==1,0], X[Y==1,1], s=50, c='red', label='Cluster 2')
plt.scatter(X[Y==2,0], X[Y==2,1], s=50, c='yellow', label='Cluster 3')
plt.scatter(X[Y==3,0], X[Y==3,1], s=50, c='blue', label='Cluster 4')
plt.scatter(X[Y==4,0], X[Y==4,1], s=50, c='orange', label='Cluster 5')

# plotting the centroids
plt.scatter(kmeans.cluster_centers_[:,0], kmeans.cluster_centers_[:,1], s=100, c='black', label='Centroids')
plt.title('Customer groups')
plt.xlabel('Annual Income')
plt.ylabel('Spending Score')
plt.show()
````
<img width="698" alt="Screenshot 2024-04-08 at 3 42 18 AM" src="https://github.com/rohitpaul1998/Customer_group_segmentation_ML/assets/113409553/9fdce696-90b1-4468-8373-95b170df94e8"><br><br>
**Insights**
- The group of customers whose annual income ranging between $10K to $20K are divided into 2 subgroups that had low and high spending scores. A group who had the same annual income had a decent spending score ranging between 60 to 100 and the group with same income had low spending scores between 10 and 40. We can infer that the group who had low spending scores in this income bracket are unlikely to spend more due to less income and in need of better offers  with reasonable prices in shopping malls than the customers who had good spending scores.<br>
- The group of customers whose annual income ranging between $70K to $140K divided into 2 subgroups that had low and high spending scores. One subgroup had the lowest spending score of 10 and the other subgroup had the highest spending score of 95, which could mean that the group who spent the least did not see reasonable offers that fell under budget. The subgroup that spent the highest are less likely to be fazed by pricy items irrespective of deals.

