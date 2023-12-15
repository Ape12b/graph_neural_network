# Node Centrality and Eigenvector Centrality

## Overview

Node centrality is a key concept in network analysis, providing a measure of the importance or influence of individual nodes within a network. One notable centrality measure is eigenvector centrality, which considers both direct and indirect connections when assessing the relative importance of nodes.

## Eigenvector Centrality

### Definition

Eigenvector centrality assigns a centrality score to each node in a network based on the principle that a node is more central if it is connected to other central nodes. This measure captures the influence of nodes that act as bridges between different parts of the network.

### Mathematical Formulation

Given an adjacency matrix \(A\) representing the connections between nodes, eigenvector centrality is obtained by finding the principal eigenvector \(x\) corresponding to the adjacency matrix. Mathematically, if \(Ax = \lambda x\), where \(x\) is the eigenvector and \(\lambda\) is the corresponding eigenvalue, then \(x\) represents the eigenvector centrality scores.

### Interpretation

- Nodes with high eigenvector centrality are not only directly connected to other important nodes but are also connected to nodes that are themselves well-connected.
- This centrality measure is particularly useful in identifying nodes that play a crucial role in connecting different parts of the network.

### Computation

Eigenvector centrality can be computed iteratively, often involving methods like the power iteration method, where the centrality scores are updated until they converge to a stable solution.

## Usage

Eigenvector centrality is a valuable tool in network analysis, providing insights into the relative importance of nodes in a network.

## Examples

```python
# Python example using NetworkX library
import networkx as nx

# Create a graph
G = nx.Graph()
G.add_edges_from([(0, 1), (1, 2), (1, 3), (2, 3)])

# Compute eigenvector centrality
centrality_scores = nx.eigenvector_centrality(G)

# Print centrality scores
print("Eigenvector Centrality Scores:")
for node, centrality in centrality_scores.items():
    print(f"Node {node}: {centrality}")


# Contributors
Apratim Bajpai
