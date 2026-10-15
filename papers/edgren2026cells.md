## Why I read it

Working with highly spatial data such as mIF is an interesting part of this research.

By proposing a two-level GNN architecture that incorporates graph convolutional networks (GCNs), self-attention graph pooling (SAGPool), and graph isomorphism networks (GINs), with or without edge features, they model both local cell interactions and higher-level tissue organization to learn representations for the downstream survival prediction task.

They also show that incorporating prior clinical knowledge, such as cancer stage (CS), as complementary information improves the prediction performance.

## Caveat

Why did they not use a heterogeneous graph, where different cell types are represented as different node types, instead of treating all cells as the same node type and encoding cell-type information as node features?

Would a heterogeneous graph better capture cell-type-specific interactions, or would it simply increase model complexity without providing a meaningful performance improvement?