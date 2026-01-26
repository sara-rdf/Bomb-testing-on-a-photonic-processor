# Bomb-testing on a photonic processor

In their 1993 paper [1], Elitzur and Vaidman (EV) proposed a now-famous interferometric “bomb-tester” thought experiment. Their protocol consists of a single particle, for instance, a photon, traversing a Mach-Zehnder interferometer where one path is obstructed by a bomb which explodes when hit by a single photon. The bomb may be a dud, meaning it is fully transparent to the photon, in which case the interferometer is arranged for destructive interference at one output. If the bomb is live, even the possibility of interaction disturbs the interference, causing the photon to end up at the “dark” output port with some probability. Detection of a photon at that port safely detects a live bomb without exploding it. This interaction-free measurement protocol can be used to detect the presence of classical, fully opaque objects (like the EV "bomb") without photon-object interaction.

In this repository, you will find Python code used to implement this curious thought experiment on [Ascella](https://www.quandela.com/resources/blog/ascella-the-single-photon-quantum-computing-prototype/) [2], a fully programmable, universal photonic processor by Quandela, hosted by the [Quandela Cloud service](https://cloud.quandela.com/). You will also find an implementation of a generalized protocol for the interaction-free detection of multiple objects proposed in our recent paper "Interaction-free measurement of multiple objects using a universal integrated photonic processor" [3]. We make use of the [Perceval framework](https://perceval.quandela.net/) for configuring the photonic chip, interfacing with the cloud and remotely retrieving experimental results directly from the device. This code can be used to reproduce the experimental results in the paper, using an error-mitigation procedure detailed in App.A2 of [3].

Usage is straightforward: Start by creating a user access token on the Quandela cloud service (consult ["Remote computing"](https://perceval.quandela.net/docs/v1.1/notebooks/Remote_Computation_Tutorial.html) tutorial in Perceval documentation to see how) and fill it in on the top of the Jupyter Notebook "Interaction-free_measurements_in_ascella_QPU" file. Also add a directory where you want the experimental data you will generate to be saved. You can then run the code, which will make calls to the remote processor, retrieve experimental data and reproduce the plots in the paper. 

Package versions used for this code:
python 3.13.5
perceval 1.0.1
numpy 1.26.4
pandas 2.3.3

References:
[1] A. Elitzur and L. Vaidman, Quantum mechanical interaction-free measurements. Found Phys 23, 987–997 (1993), doi:10.1007/BF00736012.
[2] N. Maring et al., A versatile single-photon-based quantum computing platform. Nature Photonics 18, 603–609 (2024).
[3]
