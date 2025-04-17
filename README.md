# JPEG-AIC-4 Example Dataset

url: aicdb.jpeg.org

**Repository:** `JPEG-AIC-4 Example Dataset`

## Overview

This dataset contains the test images and the subjective quality scores for the JPEG AIC-3 image quality assessmnet(IQA)dataset. 

For detailed information about the **Subjective study and the scale reconstruction methods**, see the methodology presented in the following papers:
Jenadeleh, Mohsen, Jon Sneyers, Panqi Jia, Shima Mohammadi, Joao Ascenso, and Dietmar Saupe. "Subjective Visual Quality Assessment for High-Fidelity Learning-Based Image Compression." arXiv preprint arXiv:2504.06301 (2025), https://arxiv.org/abs/2504.06301.
Testolina, Michela, Mohsen Jenadeleh, Shima Mohammadi, Shaolin Su, Joao Ascenso, Touradj Ebrahimi, Jon Sneyers, and Dietmar Saupe. "Fine-grained subjective visual quality assessment for high-fidelity compressed images." arXiv preprint arXiv:2410.09501 (2024) (Accepted at Data Compression Conference (DCC)), https://arxiv.org/pdf/2410.09501.

## Folders Descriptions:

- `full_resolution_images`: This folder contains the encoded full resolution test images and their sources.  
- `PTC_images`: This folder contains the cropped versions of the test images that were used for the subjective quality assessmnet.  


## File Descriptions

### `JPEG_AIC_reconstructed_jnd_scores.csv`

Reconstructed scores in JND units for teh percived distortion using JPEG AIC-3  test methodlogy.


#### Columns

| Column Name       | Type        | Description                                                                                      |
|-------------------|-------------|--------------------------------------------------------------------------------------------------|
| `img_num`         | Numeric     | Source image ID.                                                                                 |
| `codec`           | Numeric     | Codec used for the test image.                                                                   |
| `dlevel`          | Numeric     | Distortion level of the test image.                                                              |
| `img_source`      | Categorical | Filename of the source image.                                                                    |
| `img_distorted`   | Categorical | Filename of the compressed test image.                                                           |
| `distortion`      | Numeric     | The reconstructed subjective scale value in JND (just noticeable difference) unites.             |
| `CI_min`          | Numeric     | The lower bound of 95% confidence interval of the estimated JND score.                           |   
| `CI_max`          | Numeric     | The upper bound of 95% confidence interval of the estimated JND score.                           |                  
               
### `JPEG-AIC_metric_scores.csv`

Objective scores for the percived distortion predicted by some anchor objective image quality assessment (IQA) metrics. The scores are mapped to from the metric original scale to JND units using teh following mapping function: 

#### Columns

## Contact

Dietmar Saupe: dietmar.saupe@uni-konstanz.de

Jon Sneyers: jon@cloudinary.com

Mohsen Jenadeleh: mohsen.jenadeleh@uni-konstanz.de
