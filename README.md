# JPEG AIC-4 Example Dataset

This dataset provides an example dataset related to the [Final Call for Proposals on Objective Quality Assessment (AIC-4)](https://jpeg.org/aic/documentation.html).

The goal of the [AIC-4 activity](https://jpeg.org/aic/index.html) is to collect proposed full-reference objective image quality assessment metrics
that cover the range from good quality to lossless coding.
Such a metric quantifies perceptual differences between stimuli, in particular between a source image and a distorted image.
The proposals should target specifically distortions due to compression and not necessarily other kinds of distortions, e.g., capture, sensor, or rendering artifacts.
The proposed metrics shall estimate image quality in units of just noticeable difference (JND).

Main page: https://aicdb.jpeg.org

Relevant documents:

* [Final Call for Proposals on Objective Quality Assessment (AIC-4)](https://jpeg.org/aic/documentation.html)
* [AIC-4 Proposal Submission Template](https://jpeg.org/aic/documentation.html)
* [Common Test Condition on objective Image Quality Assessment](https://jpeg.org/aic/documentation.html)
* [Use Cases and Requirements for Image Quality Assessment v6.0](https://ds.jpeg.org/documents/jpegaic/wg1n101058-106-REQ-Use_Cases_and_Requirements_for_Image_Quality_Assessment_v6_0.pdf)



## Repository: `JPEG-AIC-4 Example Dataset`

[Download JPEG-AIC-4 Example Dataset](https://aicdb.jpeg.org/JPEG_AIC-4_Sample_Dataset.zip)


For detailed information about the Subjective study and the scale reconstruction methods, see the methodology presented in the following papers:

Jenadeleh, Mohsen, Jon Sneyers, Panqi Jia, Shima Mohammadi, Joao Ascenso, and Dietmar Saupe. "Subjective Visual Quality Assessment for High-Fidelity Learning-Based Image Compression." arXiv preprint arXiv:2504.06301 (2025), https://arxiv.org/abs/2504.06301.

Testolina, Michela, Mohsen Jenadeleh, Shima Mohammadi, Shaolin Su, Joao Ascenso, Touradj Ebrahimi, Jon Sneyers, and Dietmar Saupe. "Fine-grained subjective visual quality assessment for high-fidelity compressed images." arXiv preprint arXiv:2410.09501 (2024) (Accepted at Data Compression Conference (DCC)), https://arxiv.org/pdf/2410.09501.

### Folders Descriptions:

- `full_resolution_images`: This folder contains the encoded full resolution test images and their sources.  
- `PTC_images`: This folder contains the cropped versions of the test images that were used for the subjective quality assessmnet.  


### File Descriptions

#### `JPEG_AIC_reconstructed_jnd_scores.csv`

Reconstructed scores in JND units for the perceived distortion using the JPEG AIC-3 test methodlogy.

##### Columns

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

#### `JPEG-AIC_metric_scores.csv`

Objective scores for the percived distortion predicted by some anchor objective image quality assessment (IQA) metrics. The scores are mapped to from the metric original scale to JND units using the following mapping function: 

f(x)=(α⋅min(0,β−x)) 

##### Columns

| Column Name       | Type        | Description                                                                                      |
|-------------------|-------------|--------------------------------------------------------------------------------------------------|
| `img_distorted`   | Categorical | Filename of the compressed (test) image.                                                         |
| `img_num`         | Numeric     | Source image ID.                                                                                 |
| `codec`           | Numeric     | Codec used for the test image.                                                                   |
| `dlevel`          | Numeric     | Distortion level of the test image.                                                              |
| `distortion`      | Numeric     | The reconstructed subjective scale value in JND (just noticeable difference) unites.             |
| `metric`          | Numeric     | The perdicted quality score by the objective metric fro the test image in the original scale.    |
| `metric mapped`   | Numeric     | The mapped objective score to JND unites using a mapping function.                               |

## Contact

Dietmar Saupe: dietmar.saupe@uni-konstanz.de

Jon Sneyers: jon@cloudinary.com

Mohsen Jenadeleh: mohsen.jenadeleh@uni-konstanz.de
