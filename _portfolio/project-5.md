---
title: "Fall Project 1: Das Lab"
excerpt: "Finetuning RibonanzaNet to Predict RNA/small-molecule interactions"
collection: portfolio
---

One of the most remarkable findings from the human genome project was that while essentially all of the human genome is transcribed to RNA, only 1.5% becomes translated into proteins.[1][2] Contradicting initial hypotheses that noncoding RNAs (ncRNAs) mostly lack biological functionality, numerous research studies have demonstrated the role of introns, microRNAs, long noncoding RNAs, and numerous other ncRNAs in a variety of essential processes within cells as well as human diseases.[3][4] Indeed, ncRNAs appear to play central roles in driving the progression of many human disease phenotypes, including diverse malignancies, cardiovascular disease and neurological disorders, amongst others.[5] Despite their recognition as attractive drug targets, targeting pathogenic ncRNAs remains a challenge, currently relying on empirical small molecule screens or antisense oligonucleotides (ASOs) that have proven difficult to translate clinically.   

In recent years, deep learning models have been pivotal in the early stages of drug discovery for protein targets by effectively identifying drug binding pockets, predicting ligand-protein binding affinity (docking), and, more recently, generating de novo compounds to bind user-selected protein sequences.[6][7][8] Replication of these newer protein-target drug discovery pipeline for disease-related RNAs has not been feasible due to the lack of a sufficient RNA structural database. Compared to the approximately 200,000 experimentally determined protein structures available in the PDB, there are less than 2,000 unique RNA structures.[9] To overcome this data bottleneck of RNA structure, the Das Lab optimized a high throughput method to simultaneously probe thousands of RNA secondary structures using chemical modification reagents.[10] This method led to the Das Lab's development of the first massive RNA structural database with over 2 million RNA sequences (Ribonanza) which was used to train RibonanzaNet — a deep-learning model that successfully predicts RNA secondary structures among other chemical properties.[11]

Previously, it has been demonstrated that probing RNA transcripts with chemical modification reagents, also known as chemical mapping, can be used to identify ligand-binding regions on RNAs treated with small molecules by comparing site-specific reactivity of nucleotides. [12] My plan was to apply this proof-of-concept result with the Das Lab's high-throughput chemical mapping protocol to generate a dataset of millions to billions of RNA-ligand interactions to develop a deep learning model that predicts sequence-specific binding of small molecules. 

After demonstrating that the trained model could accurately predict both binding affinity and binding location using RNA and small molecule features, my initial goal was to fine-tune it to identify small molecule binders for pathogenic RNA targets—aiming to disrupt their structure and, consequently, their function. However, my interest gradually shifted toward designing RNA aptamers for diagnostic applications. I then set out to expand the model by incorporating a reinforcement learning framework to generate high-affinity aptamers for any given small molecule input.





