# Overview and Data Source

This repository shares a dataset with optical microscopy images of plasmonic biosensors based on gold nanoislands (AuNI) on glass substrates, to detect SARS-CoV-2 virus. It also includes extracted image features for machine learning-based detection. The images were acquired for the study by Oiticica P. R. A. et al. (2025), DOI: 10.1021/acssensors.4c03451. Computer vision methods based on handcrafted algorithms and deep-learning-based Convolutional Neural Networks (CNN) were employed for feature extraction. Machine learning models, including LDA, KNN, SVM, and RF, were trained to classify images based on SARS-CoV-2 virus concentration. The highest classification accuracy (91.6%) was achieved using the MobileNetV3_small feature extractor combined with an SVM classifier, to detect the SARS-CoV-2 virus with concentrations as low as 1 PFU/mL. This approach has potential applications for detecting other viruses and analytes.

The complete dataset were included in the repository Mendeley Data “Plasmonic immunosensor optical microscopy and machine vision to detect SARS-CoV-2 virus”, V1, doi: 10.17632/z4js67w5vc.1, available at (https://data.mendeley.com/datasets/z4js67w5vc/1). This dataset contains 858 optical microscopy images in .TIF format (RGB, 1920×2560 resolution). The images were acquired using a Zeiss Axio Lab.A1 microscope with a 40x objective (400X magnification), captured under standardized conditions.

This github repository and the above Mendeley data repo are part of the Supplementary Material of the article: "Using machine learning and optical microscopy image analysis of immunosensors made on plasmonic substrates: Application to detect SARS-CoV-2 virus", available at the [link in ACS Sensors](https://pubs.acs.org/doi/10.1021/acssensors.4c03451)

# Tables with features

The folder "Features" contains a features table for each feature extraction algorithm (in .h5 format). The table contains the information of the sample and the vector of features obtained from the original RGB image (column: "feature_vector_rgb"), and the feature vector obtained from the image converted to grayscale (column: "feature_vector_gray"). Some handcrafted methods extract features only from grayscale images (column: "feature_vector"). The complete description of the columns is given below.


table_name: algorithm name.h5 example: "MobileNetV3_small.h5"


* 'filename': image filename in the format "{sensor number}_{label_name}", where the label_name is unique and corresponds to the analyte and dilution code.
* 'label_name': unique label representing the detection test. format {analyte}_{dilution number code}
* 'concentration': Concentration in units of PFU/mL.
* 'analyte': analyte used in the test. "CoV inat" is the inactivated SARS-CoV-2 virus,  "RSV inat" corresponds to RSV virus. "No" corresponds to images of the sensor before the test (class probe), and "PBS/MCl2" represents the blank measurements. 
* 'vision_type': Feature extraction method (Handcrafted or CNN).
* 'feature_vector_rgb': The vectors of features for each image (original RGB). Each line contains a vector of type numpy.ndarray with float32 values.
* 'feature_vector_gray': the vectors of features extracted from grayscaled images. 


The table imageinfo.csv contains the first 4 columns of the feature tables.


# External Sources

Mendeley Data repo: [Plasmonic immunosensor optical microscopy and machine vision to detect SARS-CoV-2 virus](https://data.mendeley.com/datasets/z4js67w5vc/1).


# Cite

If you use this dataset, please cite our article:

Oiticica, Pedro R. A. and Angelim, Monara K. S. C. and Soares, Juliana C. and Soares, Andrey C. and Proença-Módena, José L. and Bruno, Odemir M. and Oliveira Jr, Osvaldo N.  (2025). "Using Machine Learning and Optical Microscopy Image Analysis of Immunosensors Made on Plasmonic Substrates: Application to Detect the SARS-CoV‑2 Virus". ACS Sensors. DOI: 10.1021/acssensors.4c03451.

```
@article{doi:10.1021/acssensors.4c03451,
author = {Oiticica, Pedro R. A. and Angelim, Monara K. S. C. and Soares, Juliana C. and Soares, Andrey C. and Proen{\c{c}}a-Módena, Jos{\'e} L. and Bruno, Odemir M. and Oliveira, Osvaldo N. Jr.},
title = {Using Machine Learning and Optical Microscopy Image Analysis of Immunosensors Made on Plasmonic Substrates: Application to Detect the SARS-CoV-2 Virus},
journal = {ACS Sensors},
volume = {0},
number = {0},
pages = {null},
year = {0},
doi = {10.1021/acssensors.4c03451},
    note ={PMID: 39960416},
```
