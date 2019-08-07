---
permalink: /thesis/
layout: archive
title: "Gene Tree Reconciliation Algorithm Suited For Tandem Paralogs"
---

## Links:
* [Tree Reconciliation Intro & Thesis Slide Show ](/assets/other/Thesis_SlideShow.ppsx)

* [Thesis Pdf File](/assets/pdf/Thesis_Nir_Gilad_1.0.pdf)


## Thesis Introduction:

Phylogenetic Tree Reconciliation is a powerful approach for inferring the history of 
evolutionary events leading to the occurrence of multiple homologous copies of a gene
among several species related by common ancestry, and to multiple occurrences of
homologous genes within the same species.

In the Gene\Specie tree Phylogenetic
Reconciliation problem, a phylogenetic specie tree, T_sp is constructed based on a set of
input species X, and then compared to an input phylogenetic gene tree T_g, constructed
based on a specific gene from X.

The difference between the trees may be the
consequence of evolutionary events that took place in the gene sequences, which are not
always consistent with specie evolution.

Gene duplication is an evolutionary phenomenon in which one or more genes in an organism
duplicate. Both copies of the duplicated genes then evolve independently, and the
newly duplicated gene may differentiate into new functional niches [2], Gene duplication
are known to play a major role in the evolution of almost all life on Earth.
 
 
The simplest form of duplication is tandem duplication, such that the inserted DNA
segment is identical or nearly- identical to a segment immediately bordering the
site of insertion. In the case of perfect tandem duplication, the new and old copies
of the duplicated segment are indistinguishable at the sequence level [3].
In prokaryotes, gene amplification is typically characterized as a step-wise process
initiated by tandem duplication [4].
 
Existing tree reconciliation algorithms are able to recognize duplications and the undergoing evolutionary
events on the duplicated genes, but they do not distinguish between tandem duplication resulting
in adjacent paralogs genes, and other forms of duplications.  
 
In this work, we expand the DTL tree reconciliation problem to recognize
tandem paralogous genes in the species involved, and trace their evolution
with an extended mappings and scoring model. The goal is to be able to locate
where on the specie tree the tandem paralogs were created via tandem duplication
and to follow their horizontal transfer and speciation evolutionary events throughout the specie tree.
More formally, the new phylogenetic problem is defined as follows. 
 
### Algorithm Workflow:
 
![Algorithm Workflow](/assets/images/thesis/algorithm_workflow.PNG)
 
__Definition 1: (The Tandem Paralogs (TP) reconciliation problem).__

Given a specie tree S, a gene tree G, a labeling function from leafs(G) to leafs(S).
Also given a binary relation for any two genes indicating whether they are tandem paralogs
located on the same specie or not, and a scoring function F denoting the cost of duplication,
loss, and horizontal gene transfer (HGT) events, Compute the minimal scoring scenario
mapping each vertex of G to one of the vertices of S, taking into account
the tandem paralogs information.