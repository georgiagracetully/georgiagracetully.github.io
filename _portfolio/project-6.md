---
title: "Fall Project 2: Das Lab"
excerpt: "Finetuning RibonanzaNet to Predict Ligand Binding Affinity"
collection: portfolio
---

One of the most sought after applications necessary for *de novo* design of riboswitches is to accurately predict riboswitch binding affinities to their ligands. Before the revolution of transformer-based LLMs for macromolecule structure prediction, EternaBench was created as a diverse riboswitch benchmark dataset for training and evaluation of physics-based and probabilistic ML models, including EternaFold. The designed riboswitches in this experimental dataset each included two aptamers: the first an aptamer for an input ligand and the second for an output reporter fluorescently tagged MS2 viral coat protein. These riboswitches were designed so that upon binding of the input ligand (flavin mononucleotide (FMN), theophylline, or tryptophan), the MS2 protein aptamer is more accessible, thereby increasing binding affinity of fluorescent protein. Measurements were performed on this diverse dataset for MS2 protein binding affinities with and without ligand present (K+lig and K-lig).  

[Previously](https://georgiagracetully.github.io/portfolio/project-4/), I indirectly evaluated the potential for selected probabilistic, thermodynamic, and deep learning models at predicting ligand-binding affinity through a zero-shot approach by extracting the probability of the terminal base pair in the hairpin of the MS2 protein aptamer. 

However, I furthermore wanted to fine-tune RibonanzaNet to predict ligand-binding affinity, and then evaluate predictions against models of which a constrained partition function calculation was used to predict ligand binding affinities. All riboswitches have 1 of three ligand-binding aptamers with theoretically the same binding affinity. However, the prediction task for models is to predict the binding affinity of the MS2 protein aptamer to the MS2 protein, both with and without ligand present. Here is a table of the binding affinities for each ligand : 


| Ligand       | Aptamer sequence         | Aptamer constraint            | Concentration  | K<sub>d</sub> (μM)|
|--------------|--------------------------|-------------------------------|----------------|-------------------|
| FMN          | nAGGAUAU&AGAAGGn         | (xxxxxx(&)xxxxx)              | 200 μM         | 2.2               |
| Tryptophan   | AGGACCGG&CCGCCACU        | ((xxx(((&)))xxx))             | 2.4 mM         | 1.3               |
| Theophylline | GAUACCAG&CCCUUGGCAGC     | (xxx((((&)xxx)))xxx)          | 2.0 mM         | 20                |

This table is adapted from Supplementary Table 14 from the [paper](https://www.nature.com/articles/s41592-022-01605-0#Sec36) **RNA secondary structure packages evaluated and improved by high-throughput experiments** . 


