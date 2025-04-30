---
title: "Fall Project 1: Das Lab"
excerpt: "Finetuning RibonanzaNet to Predict RNA/small-molecule interactions"
collection: portfolio
---
Previously, it has been demonstrated that probing RNA with chemical modification reagents, also known as chemical mapping or chemical footprinting, can be used to identify ligand-binding regions on RNAs comparing site-specific reactivity changes of nucleotides incubated with small molecules. [12] My plan was to apply this proof-of-concept result with the Das Lab's high-throughput chemical mapping protocol to generate a dataset of millions to billions of RNA-ligand interactions to develop a deep learning model that predicts sequence-specific binding of small molecules. 

After demonstrating that the trained model could accurately predict both binding affinity and binding location using RNA and small molecule features, my initial goal was to fine-tune it to identify small molecule binders for pathogenic RNA targets—aiming to disrupt their structure and, consequently, their function. However, my interest gradually shifted toward designing RNA aptamers for diagnostic applications or for complex biological computation. My plan was then to expand the model by incorporating a reinforcement learning framework to generate designs for high-affinity aptamers for any given small molecule input.

While I unfortunately had to forfeit this project, I did receive some preliminary results that showed that an RNA foundation model can be finetuned to predict small molecule binding events. 

A pilot experiment was performed July 2024 performing the SHAPE chemical mapping protocol on a library of 3000 RNAs designed to have pseudoknot motifs incubated with small molecules known to bind RNA - Argininamide, Erythromycin, Kanamycin, Mitoxantrone, Paromomycin, Spectinomycin, and Tetracycline. 

I fine-tuned multiple models of RibonanzaNet, adjusting hyperparameters and model architecture. At first, I tried to finetune RibonanzaNet alongside an embedding generator block so that the model could generalize beyond the initial 7 small molecules in the training data. But, the training time was taking too long (around 2 hours/epoch) for a pilot experiment with the primary goal being to test whether RibonanzaNet already contains the information necessary within RNA sequence and/or pairwise embeddings to predict interactions with small molecules (given just a small initial amount of data for training). 

The base RibonanzaNet model was trained on data from two sepearate chemical probing techniques: SHAPE (Selective Acylation of the 2' Hydroxyl as Analyzed by Primer Extension) probing with the electrophilic reagent 2-aminopyridine-3-carboxylic acid imidazolide (2A3) [13] as well as DMS chemical footprinting [14]. My initial experiment was simple: adjust the final decoder layer of RibonanzaNet to instead predict 2-8 reactivity profiles, with each reactivity profile being a new small molecule condition. I would first assess model perforance through quick visual checks on heat maps of experimental and predicted reactivity profiles under each condition. If the predictions looked promising, I would then generate a more robust quantitative analysis to benchmark model predictions. 

## The Experiment 

Experimental Null Hypothesis: RibonanzaNet cannot be finetuned on 1k new labeled examples of RNA/small-molecule chemical reactivity profiles to make accurate predictions on the test data. 

Possible explanations of Null Hypothesis: 
1) The experimental data itself is pure noise. There is no predictable pattern that even a million-parameter LLM can learn. 
2) The model needs more diverse training data to learn. 
3) The model needs more parameters or a more sophisticated architecture tailored to the new task in order to learn RNA-small molecule reactivity profiles . 

## Selected Results - Qualitative 

The best results qualitatively from this pilot experiment came from RibonanzaNet-SM 005. This model was trained with a final decoder layer of 8 reactivity profiles, the first seven being *reactivity differences* between the small molecule condition and a no small molecule baseline (I called this baseline "NoDr" for "No Drug", since all of these molecules are drugs). The last vector was the absolute reactivity profile without small molecule incubation. The idea is that since I used MSE or MCRSE as the loss function during training, adding in the absolute reactivity vector would normalize the gradient so that the model would not overfit to the data with the largest magnitude of reactivity differences. However, as you will see with my quantitative results, this still became a problem as there was a direct correlation in magnitude of reactivity differences with the PCC of predictions under each drug condition. But again, this was just a preliminary experiment to evaluate whether RibonanzaNet contained information necessary within the pretrained model to make predictions under new conditions. Ideally, since this model is relatively sparse and easy to train, it would be used my experimentalists with small datasets for finetuning to predict RNA behavior under other conditions. Alternatively, we would collect enough new RNA reactivity profiles with different small molecules so that, combined with an LLM 

Here are some selected quantitative results , however, you can play around with generating heatmaps of all RNAs in the test dataset under each condition by copying this repository [INSERT REPO OF ALL TEST DATA AN DJUPYTER NBS] . 

An example of different experimental and predicted reactivity *differences* on a sequence from the test set : 

<br/><img src='/images/normalized_005_sequence_13.png'>"



<div style="display: flex; justify-content: center; gap: 20px;">
  <img src="/images/eryt_qual_004.png" style="width: 45%;">
  <img src="/images/eryt_qual_005.png" style="width: 45%;">
</div>








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





