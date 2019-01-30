# Notes for the CheXpert Project

## Introduction

The details of the CheXpert project are available at [this](https://stanfordmlgroup.github.io/competitions/chexpert/) link.

### Output Detail

The project is a multi-class classification problem. It has 14 output classes, which are as follows:
1. No Finding
2. Enlarged Cardiomediastinum
3. Cardiomegaly
4. Lung Opacity
5. Lung Lesion
6. Edema
7. Consolidation
8. Pneumonia
9. Atelectasis
10. Pneumothorax
11. Pleural Effusion
12. Pleural Other
13. Fracture
14. Support Decices

### Input Detail

In total, there are 223414 samples are provided.

The input to the model are x-ray images of the chest of the patients. The x-rays are either taken from a frontal position, or from a lateral position. The distribution of frontal vs. lateral is as follows:
1. Frontal: 191027 samples
2. Lateral: 32387 samples

In addition, the age of the patient has been provided.

And lastly, the gender of the patient has been provided. The distribiution of male vs. female is as follows:
1. Male: 132636 samples
2. Female: 90777 samples
3. Unknown: 1

### Some Initial Thoughts and Questions

1. I need to find other models that have been found to be successful for x-ray imaging
- It might be worth to start with transfer learning, by simply changing the size of the input and output layers.
2. Is there a distinction required for the frontal vs. lateral scans?
3. Is there a distinction required between male and female?
- First try by not considering the gender of the patient.
- If that does not provide good results, then try to create a model that considers the gender.
4. What impact does the age of the patient have on the results?
- Initially start without considering the age of the patient.
- If that does not provide good results, then try to create a model that considers the age.
5. As this is an imaging problem, the best solution probably requires a CNN. 
6. Figure out an efficient data pipeline for images.
7. Figure out which cloud GPU service to use. It will not be possible to do the learning on my laptop, especially not for the uncompressed images, which is the final goal.