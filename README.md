# tRCM-Dataset

Route choice dataset with various scenarios. Collected by Georgia Tech ACT Lab through driving simulator experiments. 

## Data Description

The dataset contains a list of tensor objects. Each tensor represents a route choice sample collected through driving simulator experiements, which is represented as [a graph in pytorch-geometric](https://pytorch-geometric.readthedocs.io/en/latest/notes/introduction.html#data-handling-of-graphs). Specifically, there are four attributes in a tensor `data`:

- `data.x`: Node feature matrix with shape `[num_nodes, num_node_features]`. The columns from left to right are travel time, congestion level, and turn indicator.
- `data.y`: Target to train against with shape `[num_nodes]`. The `1` element in `data.y` indicates the route choice in this sample.
- `data.edge_attr`: Graph connectivity in COO format with shape `[2, num_edges]`.
- `data.edge_index`: Edge feature matrix with shape `[num_edges]`. The edge feature is the route similarity index calculated from the overlapping links. 

## Acknowledgement

This research is funded by NSF \# 1662692.
