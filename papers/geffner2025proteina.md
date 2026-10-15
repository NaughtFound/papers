## Why I read it

I read this paper to understand how **flow matching** works for protein backbone generation. I found it interesting to see how flow matching is combined with a scalable **Transformer architecture** and hierarchical conditioning.

The architecture has three important components:

- **Create Sequence Representation**
- **Create Sequence Conditioning**
- **Create Pair Representation**

The pair representation is particularly interesting because it provides pairwise structural information that is used within the Transformer to model relationships between residues. The model also uses hierarchical fold-class labels for controllable generation.

## Caveat

Could we incorporate **causal or other relational information** into the pair representation?

The current pair representation mainly captures structural and positional relationships between residues. It would be interesting to investigate whether explicitly representing different types of biological relationships could provide a useful inductive bias.

For example:

> Would modeling relationships as typed or causal relations improve protein structure generation or controllability?

However, causal relationships may be less straightforward than relational ones in this setting. A **relational representation** seems more natural because residues can have different types of structural or biological interactions, while introducing causality would require a clear definition of what the causal direction represents.