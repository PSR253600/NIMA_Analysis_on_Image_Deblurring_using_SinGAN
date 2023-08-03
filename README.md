# Neural Image Quality Assessment Analysis on Image Deblurring using SinGAN
This is a study on quality of the SinGAN generated images from a blurry image with different generation start scales. It mainly focuses on two quality metrics. They are Neural Image Quality Assessment (NIMA) Score and Peak Signal to Noise Ratio (PSNR).


# Dataset used
A publicly available dataset comprised of 1050 blurred and sharp images (350 triplets) i.e., each image is a set of three photos of the same scene: sharp, motion-blurred and defocused-blurred images.

The dataset was created to validate the blur detection algorithm.

Check-out the following links to download the dataset:

[Link to download from Kaggle](https://www.kaggle.com/kwentar/blur-dataset)

[Link to download from Google Drive](https://drive.google.com/file/d/1RObmCDPeQ1Lg-V6u7dT02Pf0qH-QMcTp/view)


# Process Workflow
Select few triplets from the dataset to perform analysis using them. Here, I selected 122_HONOR-7X and 346_HUAWEI-MATE20 triplets.

Choose one of the triplets and perform as follows:
1. Train the SinGAN architecture with the original sharp image.
2. Generate random samples from the SinGAN's multi-scale GAN architecture with different generation start scales by initially, providing motion-blurred image to it  and then, providing defocused-blurred image to it.
3. Compute NIMA Scores and PSNRs for every random sample generated.

Repeat the above process for every selected triplet.


# File description and working
`122_HONOR-7X_S.jpg`, `346_HUAWEI-MATE20_S.jpg` are sharp images.

`122_HONOR-7X_M.jpg`, `346_HUAWEI-MATE20_M.jpg` are motion-blurred images.

`122_HONOR-7X_F.jpg`, `346_HUAWEI-MATE20_F.jpg` are defocused-blurred images.

`SinGAN.ipynb` is an executable Jupyter Notebook, which is a reference to the official implementation of SinGAN architecture, to train the SinGAN architecture with a sharp image, generate random samples with different generation start scale from a blurred image and save them in the drive.

`Image_Quality_Assessment.ipynb` is an executable Jupyter Notebook, which is a reference to an implementation of pre-trained model on AVA dataset, to compute NIMA scores and PSNR values for every random sample.

`122_HONOR-7X_M_256x256_randomsamples.zip` is a zip file comprises of random samples (with different generation scales) generated from the SinGAN architecture (trained with `122_HONOR-7X_S.jpg`) when `122_HONOR-7X_M.jpg` is provided as an input.

`122_HONOR-7X_F_256x256_randomsamples.zip` is a zip file comprises of random samples (with different generation scales) generated from the SinGAN architecture (trained with `122_HONOR-7X_S.jpg`) when `122_HONOR-7X_F.jpg` is provided as an input.

`346_HUAWEI-MATE20_M_256x256_randomsamples.zip` is a zip file comprised of random samples (with different generation scales) generated from the SinGAN architecture (trained with `346_HUAWEI-MATE20_S.jpg`) when `346_HUAWEI-MATE20_M.jpg` is provided as an input.

`346_HUAWEI-MATE20_F_256x256_randomsamples.zip` is a zip file comprises of random samples (with different generation scales) generated from the SinGAN architecture (trained with `346_HUAWEI-MATE20_S.jpg`) when `346_HUAWEI-MATE20_F.jpg` is provided as an input.

`NIMAScores_and_PSNRs.zip` is a zip file comprised of csv files and pdf documents, which contains NIMA metrics and PSNRs, for random samples generated from different generation start scales.

`NIMA_analysis.pptx` is a ppt file that provides the entire detailing about the NIMA analysis and SinGAN architecture.


# Note
I used a standard fixed size of 256x256 px for every image to extract unbiased quality scores from the images.

Number of generation scales used to build SinGAN architecture: 10

Up-scale factor used: 0.75


# Related Sources
[Kwenter blur_dataset](https://github.com/Kwentar/blur_dataset)

[Tamarott SinGAN](https://github.com/tamarott/SinGAN)

[aigagror ML-Aesthetics-NIMA](https://github.com/aigagror/ML-Aesthetics-NIMA)

[Tamarott SinGAN page](https://tamarott.github.io/SinGAN.htm)