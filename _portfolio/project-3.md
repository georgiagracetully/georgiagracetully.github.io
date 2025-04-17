---
title: "Summer Project 1: Das Lab"
excerpt: "Evaluating heterogeneity algorithms on ROOL RNA<br/><img src='/images/summer_proj_image.png'>"
collection: portfolio
---

One of the most exciting structures solved by Rachael Kretsch using cryo-EM was the naturally ornate, RNA-only complex ROOL. Interestingly, this cage-like octamer appeared to be found in two dominant conformations: "open" and "closed" from simple 2D and 3D classification algorithms. However, it was unknown whether there might be a noticable trajectory of intermediate states captured within the 2D micrographs. This summer I spent a few weeks using four cryo-EM heterogeneity algorithms: 3DVariability (cryoSPARC), 3DFlex (cryoSPARC), cryoDRGN, e2gmm to evaluate 1) whether there could possibly be intermediate states present within the stack of particles and 2) whether each algorithm separated the particles into the same clusters. 

Based on cluster profiles from all algorithms, we concluded that only two dominant states were present in the particle stack. To see how each novel algorithm clustered particles (color labelled by the initial 3D classification job ), you can copy the making_plots directory in /notebooks folder, and then interactively play around with Making_plots.ipynb. 

[View Notebook](https://github.com/georgiagracetully/georgiagracetully.github.io/blob/master/notebooks/making_plots/Making_plots.ipynb)

<br/><img src='/images/image9.png'>" <br/><img src='/images/image10.png'>
Pretty obvious from images above which conformation is "open" or "closed" . 

<br/><img src='/images/summer_proj_image.png'>
Probing the conformational landscapes of ROOL particles from open and closed classes separately with heterogeneity algorithms. Figure on the left represents a simplified energy landscape of ROOL (blue) superimposed with an estimated relative population of states (red) to illustrate the hypothesis that open and closed conformations represent favorable thermodynamic states separated by a kinetic barrier. Figures on the right represent individual simplified energetic landscapes of the open (top, pink) and closed (bottom, yellow) states with black lines representing an estimated relative population of particles in corresponding states. Our analysis changed from trying to recover states within the poorly populated red region between both open and closed states (left), to the lowly populated peripheral regions of either primary structure (right).

Here is a write-up of selected results in a summary analysis. This work was performed in the Das Lab. 

[📄 View PDF ROOL heterogeneity project](/files/Tully_Summer_Project_summary.pdf)

Paper recently released in the archive: 
(1)	Kretsch, R. C.; Wu, Y.; Shabalina, S. A.; Lee, H.; Nye, G. P.; Koonin, E. V.; Gao, A.; Chiu, W.; Das, R. Naturally Ornate RNA-Only Complexes Revealed by Cryo-EM. bioRxiv, 2024, 2024.12.08.627333. https://doi.org/10.1101/2024.12.08.627333.
