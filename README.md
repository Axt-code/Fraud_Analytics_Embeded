# Graph Embedding and Clustering with Node2Vec, Spectral, and GCN
## Project Overview
This project focuses on embedding techniques to represent graph data and cluster the nodes within the graph. The embeddings were generated using Node2Vec, Spectral Embedding, and Graph Convolutional Networks (GCN). The dataset used represents payment transactions, and K-means clustering was applied to identify potential clusters in the data.

## Dataset
The dataset used for this project is Payments.csv, which consists of three columns:

Sender: ID of the sender in the transaction.
Receiver: ID of the receiver in the transaction.
Amount: The amount of money transferred.
Each row represents a transaction between the sender and receiver, where the Sender sends a specific Amount to the Receiver.

## Graph Construction
The payment dataset was transformed into a graph where:

Nodes: Represent the Sender and Receiver IDs.
Edges: Represent the transaction between a Sender and Receiver, with the Amount as the edge weight.
For multiple transactions between the same pair, the amounts were averaged and used as the final edge weight.
Embedding Methods
1. Node2Vec
Node2Vec generates feature representations of nodes using random walks on the graph.
Steps:
Perform random walks on the graph.
Use the random walks to train a skip-gram model and generate node embeddings.
Dimensionality reduction using PCA from 8 dimensions to 3 for visualization.
2. Spectral Embedding
Spectral Embedding reduces the data's dimensionality using the eigenvalues of the graph's adjacency matrix.
Steps:
Create the Adjacency Matrix from the graph.
Calculate the Degree and Laplacian matrices.
Find the Eigenvectors of the Laplacian matrix.
Use the top three Eigenvectors as the node embeddings.
3. Graph Convolutional Network (GCN)
GCN uses the graph’s structural information to enhance the embedding generation process.
Steps:
Create a directed graph from the data.
Implement a GCN model with convolutional layers and train it on the graph to obtain the node embeddings.
Clustering with K-Means
After obtaining the embeddings, K-Means clustering was applied to identify clusters in the dataset.
Since the dataset includes both fraud and non-fraud data, we set the number of clusters to 2.
Each embedding method produces different clusters depending on the hyperparameters.
Results
The node embeddings generated by each technique were visualized in 3D and clustered using K-Means:

Figure 1: Node2Vec Embedding Clusters
Figure 2: GCN Embedding Clusters
Figure 3: Spectral Embedding Clusters
## Conclusion
This project demonstrates how various embedding techniques can represent graph data and how clustering can reveal meaningful patterns, such as potential fraudulent transactions. The embeddings generated from Node2Vec, Spectral, and GCN offer different perspectives on the structure and relationships within the transaction network.

## How to Run the Project
Preprocess the dataset by constructing the graph.
Generate embeddings using the Node2Vec, Spectral, and GCN methods.
Apply K-Means clustering on the embeddings to find clusters.
Visualize the clusters for each embedding technique.

## Dependencies
Python 3.x
NumPy
Pandas
SciPy
Scikit-learn
PyTorch (for GCN implementation)
NetworkX
Matplotlib (for visualization)
