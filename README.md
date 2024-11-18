# RSNA-MICCAI 2021 Brain Tumor Challenge

## 1. 📂Dataset download
  - Download task 1 data (BraTS21 3D tumor segmentation dataset) and extract to *data/task1_data* from url: https://www.kaggle.com/dschettler8845/brats-2021-task1 (Credit for Darien Schettler who uploaded it). The directory contains something like:
    - BraTS2021_00000/
    - BraTS2021_00002/
    - BraTS2021_00003/
    - ....
  -Change the Setting Json in Segmentation and Traning code as per your directory.

## 2. 🧠 Network Architecture

![Stage1](https://github.com/user-attachments/assets/2e948b01-8ca0-4661-a9e8-aab520739a1f)

- We inspire our architecture from Unet model where we use DenseNet121 as our encoder or also know as Backbone Model for more depth feature extraction and nn-Unet++ (no new Unetplusplus)as our decoder for reconstructing final output image.

## 3.🔄 Data Preprocessing Steps:
- Converted all 3D images into 2D slices using NIfty Image module and then stored in numpy format.
- All numpy slices were overlayed by segmentation masks.

## 4. 🔄 Data Augmentation
Dynamic augmentations were applied to each image during training to improve generalization:
Random rotation
Horizontal and vertical flipping
Brightness adjustments

## 5.Model Link:
- [DenseNet121](https://example.com/link-to-your-model)
- [Kaggle](https://example.com/link-to-your-model)



## 5. ⚙ Training Process
Initialization: Models initialized with DenseNet121 without pretrianed weights.
Early Stopping: Halted training based on validation loss to avoid overfitting.
Loss Function: Dice loss.
Hardware: Training executed on Kaggle GPU (P100) for efficiency.

## 6. 📊 Evaluation Metrics
The models were evaluated using:
- IOU
- Dice Loss

## 7. Tools & Libraries
- All were mentoined in the requirment.txt

*🤝 Contributing*
Contributions are welcome! Please open an issue or submit a pull request for any improvements.

*📧 Contact*
For any queries, feel free to reach out at mohit.g@ihub-data.iiit.ac.in





