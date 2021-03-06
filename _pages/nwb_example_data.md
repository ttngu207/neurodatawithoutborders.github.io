---
title: "NWB:N Example Data"
layout: default
excerpt: "NWB:N Example Data"
sitemap: false
permalink: /exampledata
---


# Example NWB:N Data

This is a list of example NWB:N files. This is not a comprehensive list
and provided as a convenience. Many of the datasets and tools are built
and supported by other groups, and are in active development.

**Disclaimer:** Reference herein to any specific data, product, process, or service by its trade name, trademark, manufacturer, or otherwise, does not constitute or imply its endorsement, recommendation, or favoring by the NWB:N development team, United States Government or any agency thereof, or The Regents of the University of California. Use of the NeurodataWithoutBorders name for endorsements is prohibited.

## Allen Institute for Brain Science: pre-release (May, 2019)

A collection of *pre-release* example datasets is available for
download [here](http://download.alleninstitute.org/informatics-archive/prerelease/):
* <img src="../images/EphysVisualCoding.PNG" height="100">  Passive viewing extracellular electrophysiology
* <img src="../images/OphysVisualBehavior.PNG" height="100">  Visual behavior calcium imaging 
* <img src="../images/ICEphys.PNG" height="75"> Intracellular in-vitro electrophysiology 

## Frank Lab (UCSF) (May, 2019)

A version of Frank Lab HC06 dataset from CRCNS.org (see the [dataset about page](https://crcns.org/data-sets/hc/hc-6/about-hc-5)) is available at [Bon04.nwb](https://www.dropbox.com/s/92jkkse2c7lm7qe/bon04.nwb?dl=0) (~4GB). The NWB:N file is created by [create_franklab_nwbfile.ipynb](https://github.com/LorenFrankLab/franklab-nwb-hack/blob/master/hackathon-6/create_franklab_nwbfile.ipynb). The [franklab-nwb-hac](https://github.com/LorenFrankLab/franklab-nwb-hack/tree/master/hackathon-6) repository also contains additional notebooks demonstrating query and analysis of this dataset as well of the ecephys_session_785402239.nwb  file from the May, 2019 Allen Institute for Brain Science: pre-release above.

## Buzsaki Lab (NYU) (May, 2019)
Electrophysiology recordings from hippocampal regions of mice in theta-maze and in open exploration, from [Senzai, Yuta, and György Buzsáki. "Physiological properties and behavioral correlates of hippocampal granule cells and mossy cells." Neuron 93.3 (2017): 691-704.](http://www.buzsakilab.com/content/PDFs/Senzai2017Neuron.pdf)

Data can be found [here](https://buzsakilab.nyumc.org/datasets/NWB/SenzaiNeuron2017/) and is in beta-release (data is correct but file organization may change slightly).

## Svoboda Lab (Janelia Research Campus) (January, 2019)
An ongoing DataJoint-NWB interoperability project showcasing data with DataJoint pipeline and exported NWB 2.0 files is presented at [DataJoint-NWB-Showcase](https://github.com/vathes/DataJoint-NWB-showcase)

This project involves data from 11 published studies from ***Svoboda Lab (Janelia Research Campus)*** 

## PyNWB Test Data

PyNWB generates as part of its test suite a collection of small NWB:N files with synthetic test data. The files generated by the tests are available [here](https://drive.google.com/drive/folders/1g1CpnoMd9s9L-sHBWVyklp3-xJcLGeFt?usp=sharing)

## Svoboda Lab (Janelia Research Campus)
An ongoing DataJoint-NWB interoperability project showcasing data with DataJoint pipeline and exported NWB 2.0 files is presented at [DataJoint-NWB-Showcase](https://github.com/vathes/DataJoint-NWB-showcase)

This project involves data from 11 published studies from ***Svoboda Lab (Janelia Research Campus)***


## Churchland Lab (Cold Spring Harbor Laboratory)

Calcium imaging dataset accompanying the paper:
>Farzaneh Najafi, Gamaleldin F Elsayed, Robin Cao, Eftychios Pnevmatikakis, Peter E Latham, John Cunningham, Anne K Churchland. "Excitatory and inhibitory subnetworks are equally selective during decision-making and emerge simultaneously during learning" bioRxiv (2018): 354340.

The repository for the dataset can be found [here](http://repository.cshl.edu/37693/)

The code for generating this dataset in NWB 2.0 format, as well as the demostration of using these files (in python) can be found at [najafi-2018-nwb](https://github.com/vathes/najafi-2018-nwb). For demo in MATLAB, see [najafi-2018-matlab](https://github.com/vathes/najafi-2018-matlab)