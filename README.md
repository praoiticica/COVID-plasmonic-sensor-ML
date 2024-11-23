# Project: Development of a plasmonic immmunosensor to detect the SARS-CoV-2 virus using optical microscopy and Machine vision.

The data included in this repository is part of the Supplementary Materials  for the article: "Using machine learning and optical microscopy image analysis of immunosensors made on plasmonic substrates: Application to detect SARS-CoV-2 virus"


In this work, we developed a plasmonic immunosensor with a plasmonic substrate composed of gold nanoisland onto glass (AuNI/glass substrate) and we functionalized the substrate with the anti-spike S1 protein of the SARS-CoV-2 virus. We performed detection tests with solutions containing inactivated, SARS-CoV-2 virus particles with concentrations from 1x10<sup>-4</sup> to 1x10<sup>5</sup> PFU/mL The negative tests were performed with blank solutions, and solutions containing inactivated Respiratory syncytial virus (RSV). The detection was performed with optical microscopy and image analysis with computer vision and machine learning classification. This immunosensor was able to detect and classify the SARS-CoV-2 virus with concentration from 1 PFu/mL to 1x10<sup>5</sup>PFU/mL with an accuracy of 91.6 % using the model MobileNetV3_small for image features extraction and the model SVM for classification. We compared various feature extraction methods based on handcrafted algorithms and CNN architectures. For more details on the materials, methods and results, check the complete manuscript and the supplementary materials (We will provide a link soon...)

# Usage

We included in this repository:

* A link for the optical microscopy images of the plasmonic sensors before and after the detection tests analyzed in this work. The original optical microscopy images can be downloaded at: [image dataset](https://drive.google.com/drive/folders/1sB3stEALITgml_QzeLOjtAJEfh7Wyp1C?usp=sharing)

* The results of the features extraction step using the handcrafted algorithms and CNN architectures (pre-trained in ImageNet) configured as features extractors.


For each feature extraction algorithm, we generated a features table in .h5 format. This table contains the information of the sample (filename, )and the vector of features obtained from the original RGB image (column: "feature_vector_rgb"), and the feature vector obtained from the image converted to grayscale (column: "feature_vector_gray"). Some handcrafted methods extract features only from grayscale images (column: "feature_vector"). The complete description of the columns is given below.


table_name: {algorithm name}_{implementation}.h5 example: "MobileNetV3_small_pytorch.h5"


* 'filename': image filename in the format "{sensor number}_{label_name}", where the label_name is unique and corresponds to the analyte and concentration used in the test.
* 'label_name': unique label representing the detection test. format {analyte}_{number of dilutions}
* 'concentration': Concentration in units of PFU/mL.
* 'analyte': analyte used in the test. No corresponds to images of the sensor before the test (probe), and blank measurements. PBS/MCl2 is the buffer used in the blank measurements. CoV inat is the inactivated SARS-CoV-2 virus and RSV inat was used in negative tests. 
* 'label_number2': 0 for positive and 1 for negative. Used in binary classifications.
* 'label_name2': Positive or Negative.
* 'vision_type': The type of algorithm used in the image features extraction. It can be either handcrafted or CNN.
* 'feature_vector_rgb': The vectors of features for each image (original RGB). Each line contains a vector of type numpy.ndarray with float32 values.
* 'feature_vector_gray': the vectors of features extracted from grayscaled images. 


# Cite

If you use this data, please cite our paper
