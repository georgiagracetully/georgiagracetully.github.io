---
title: "Fall Project 1: Das Lab"
excerpt: "Finetuning RibonanzaNet to Predict RNA/small-molecule interactions"
collection: portfolio
---

One of the most remarkable findings from the human genome project was that while essentially all of the human genome is transcribed to RNA, only 1.5% becomes translated into proteins.[1][2] Contradicting initial hypotheses that noncoding RNAs (ncRNAs) mostly lack biological functionality, numerous research studies have demonstrated the role of introns, microRNAs, long noncoding RNAs, and numerous other ncRNAs in a variety of essential processes within cells as well as human diseases.[3][4] Indeed, ncRNAs appear to play central roles in driving the progression of many human disease phenotypes, including diverse malignancies, cardiovascular disease and neurological disorders, amongst others.[5] Despite their recognition as attractive drug targets, targeting pathogenic ncRNAs remains a challenge, currently relying on empirical small molecule screens or antisense oligonucleotides (ASOs) that have proven difficult to translate clinically.   

In recent years, deep learning models have been pivotal in the early stages of drug discovery for protein targets by effectively identifying drug binding pockets, predicting ligand-protein binding affinity (docking), and, more recently, generating de novo compounds to bind user-selected protein sequences.[6][7][8] Replication of these newer protein-target drug discovery pipeline for disease-related RNAs has not been feasible due to the lack of a sufficient RNA structural database. Compared to the approximately 200,000 experimentally determined protein structures available in the PDB, there are less than 2,000 unique RNA structures.[9] To overcome this data bottleneck of RNA structure, the Das Lab optimized a high throughput method to simultaneously probe thousands of RNA secondary structures using chemical modification reagents.[10] This method led to the Das Lab's development of the first massive RNA structural database with over 2 million RNA sequences (Ribonanza) which was used to train RibonanzaNet — a deep-learning model that successfully predicts RNA secondary structures among other chemical properties.[11]

Previously, it has been demonstrated that probing RNA transcripts with chemical modification reagents, also known as chemical mapping, can be used to identify ligand-binding regions on RNAs treated with small molecules by comparing site-specific reactivity of nucleotides. [12] My plan was to apply this proof-of-concept result with the Das Lab's high-throughput chemical mapping protocol to generate a dataset of millions to billions of RNA-ligand interactions to develop a deep learning model that predicts sequence-specific binding of small molecules. 

After demonstrating that the trained model could accurately predict both binding affinity and binding location using RNA and small molecule features, my initial goal was to fine-tune it to identify small molecule binders for pathogenic RNA targets—aiming to disrupt their structure and, consequently, their function. However, my interest gradually shifted toward designing RNA aptamers for diagnostic applications or for complex biological computation. My plan was then to expand the model by incorporating a reinforcement learning framework to generate designs for high-affinity aptamers for any given small molecule input.

While I unfortunately had to forfeit this project, I did receive some preliminary results that showed that an RNA foundational model can be finetuned to predict small molecule binding events. 

A pilot experiment was performed July 2024 performing the SHAPE chemical mapping protocol on a library of 3000 RNAs designed to have pseudoknot motifs incubated with small molecules known to bind RNA - Argininamide, Erythoromycin, Kanamycin, Mitoxantrone, Paromomycin, Spectinomcin, and Tetracycline. 







(1)	Clamp, M.; Fry, B.; Kamal, M.; Xie, X.; Cuff, J.; Lin, M. F.; Kellis, M.; Lindblad-Toh, K.; Lander, E. S. Distinguishing Protein-Coding and Noncoding Genes in the Human Genome. Proc. Natl. Acad. Sci. U. S. A. 2007, 104 (49), 19428–19433. 

(2)	Schadt, E. E.; Edwards, S. W.; GuhaThakurta, D.; Holder, D.; Ying, L.; Svetnik, V.; Leonardson, A.; Hart, K. W.; Russell, A.; Li, G.; Cavet, G.; Castle, J.; McDonagh, P.; Kan, Z.; Chen, R.; Kasarskis, A.; Margarint, M.; Caceres, R. M.; Johnson, J. M.; Armour, C. D.; Garrett-Engele, P. W.; Tsinoremas, N. F.; Shoemaker, D. D. A Comprehensive Transcript Index of the Human Genome Generated Using Microarrays and Computational Approaches. Genome Biol. 2004, 5 (10), R73. 

(3)	Palazzo, A. F.; Lee, E. S. Non-Coding RNA: What Is Functional and What Is Junk? Front. Genet. 2015, 6, 2. 

(4)	Richard Boland, C. Non-Coding RNA: It’s Not Junk. Dig. Dis. Sci. 2017, 62 (5), 1107–1109. 

(5)	Nemeth, K.; Bayraktar, R.; Ferracin, M.; Calin, G. A. Non-Coding RNAs in Disease: From Mechanisms to Therapeutics. Nat. Rev. Genet. 2024, 25 (3), 211–232. 

(6)	Kozlovskii, I.; Popov, P. Spatiotemporal Identification of Druggable Binding Sites Using Deep Learning. Commun. Biol. 2020, 3 (1), 618. 

(7)	Yang, C.; Chen, E. A.; Zhang, Y. Protein-Ligand Docking in the Machine-Learning Era. Molecules 2022, 27 (14), 4568. 

(8)	Krishnan, S. R.; Bung, N.; Bulusu, G.; Roy, A. Accelerating DE Novo Drug Design against Novel Proteins Using Deep Learning. J. Chem. Inf. Model. 2021, 61 (2), 621–630. 

(9)	Berman, H. M. The Protein Data Bank. Nucleic Acids Res. 2000, 28 (1), 235–242. 

(10)Seetin, M. G.; Kladwang, W.; Bida, J. P.; Das, R. Massively Parallel RNA Chemical Mapping with a Reduced Bias MAP-Seq Protocol. In Methods in Molecular Biology; Humana Press: Totowa, NJ, 2014; pp 95–117.

(11) He, S.; Huang, R.; Townley, J.; Kretsch, R. C.; Karagianes, T. G.; Cox, D. B. T.; Blair, H.; Penzar, D.; Vyaltsev, V.; Aristova, E.; Zinkevich, A.; Bakulin, A.; Sohn, H.; Krstevski, D.; Fukui, T.; Tatematsu, F.; Uchida, Y.; Jang, D.; Lee, J. S.; Shieh, R.; Ma, T.; Martynov, E.; Shugaev, M. V.; Bukhari, H. S. T.; Fujikawa, K.; Onodera, K.; Henkel, C.; Ron, S.; Romano, J.; Nicol, J. J.; Nye, G. P.; Wu, Y.; Choe, C.; Reade, W.; Eterna participants; Das, R. Ribonanza: Deep Learning of RNA Structure through Dual Crowdsourcing. bioRxivorg 2024.

(12) Martin, S.; Blankenship, C.; Rausch, J. W.; Sztuba-Solinska, J. Using SHAPE-MaP to Probe Small Molecule-RNA Interactions. Methods 2019, 167, 105–116. 





