---
title: "Rotation Project 1: Rotskoff Group"
excerpt: "Using Neural Networks for Quantum MD Simulations <br/><img src='/images/rot_proj_1_image.png'>"
collection: portfolio
---

Here are the slides of my first rotation project at Stanford, in the Rotskoff group. I wrote my own implementation of Schrodinger Network (in a way that made the most sense to me, a ML and PyTorch novice), and then ran some tests using a training dataset of DFT calcuations on a simple system of 16 water molecules. 

The coolest thing about this network is that the model is trained not only on the labels (in this case, the energies computed via DFT), but also on the energy gradients. In physics, the gradient of a system's energy with respect to atomic positions corresponds to the forces acting on the atoms. These learned forces can then be used to accelerate molecular dynamics (MD) simulations, while still capturing quantum mechanical interactions.

[📄 View PDF of PowerPoint Slides](/files/Schnet_Architecture.pdf)
