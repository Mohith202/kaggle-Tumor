# RSNA-MICCAI 2021 Brain Tumor Challenge

## 1. 📂Dataset download
  - Download task 1 data (BraTS21 3D tumor segmentation dataset) and extract to *data/task1_data* from url: https://www.kaggle.com/dschettler8845/brats-2021-task1 (Credit for Darien Schettler who uploaded it). The directory contains something like:
    - BraTS2021_00000/
    - BraTS2021_00002/
    - BraTS2021_00003/
    - ....
  -Change the Setting Json code as per your directory.




*🧠 Network Architecture*
![Stage1](https://github.com/user-attachments/assets/2e948b01-8ca0-4661-a9e8-aab520739a1f)
--We inspire our architecture from Unet model where we use DenseNet121 as our encoder or also know as Backbone Model for more depth feature extraction and nn-Unet++ (no new Unetplusplus)as our decoder for reconstructing final output image.

*🔄 Data Preprocessing*
Steps:
-Converted all 3D images into 2D slices using NIfty Image module and then stored in numpy format.
-All numpy slices were overlayed by segmentation masks.

*🔄 Data Augmentation*
Dynamic augmentations were applied to each image during training to improve generalization:
Random rotation
Horizontal and vertical flipping
Brightness adjustments

*⚙ Training Process*
Initialization: Models initialized with ImageNet pre-trained weights.
Optimizer: Used Adam optimizer with an initial learning rate of 
Learning Rate Scheduler: Dynamically adjusted learning rates for effective convergence.
Early Stopping: Halted training based on validation performance to avoid overfitting.
Loss Function: Cross-entropy loss for multi-class classification.
Hardware: Training executed on Kaggle GPU (P100) for efficiency.

*📊 Evaluation Metrics*
The models were evaluated using:
Sensitivity
Specificity
Area Under the Receiver Operating Characteristic (AUROC) Curve

*🚀 Results*
The ensemble model demonstrated:
Improved classification accuracy across all stages of DR.
Reduced variance in predictions for more stable performance.

*📂 Repository Structure*
 bash
├── notebooks/                # Jupyter notebooks for EDA and experimentation  
├── README.md                 # Project documentation 

*Tools & Libraries*

tensorflow==2.12.0

numpy==1.23.1

pandas==1.5.2

scikit-learn==1.0.2

matplotlib==3.5.0


*🔗 References*

APTOS 2019 Blindness Detection Dataset: Kaggle Challenge [APTOS DATASET](https://www.kaggle.com/competitions/aptos2019-blindness-detection)

EfficientNet: Paper [EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks](https://arxiv.org/abs/1905.11946)

Reproducing the Paper[Deep Learning-Based Detection of Referable Diabetic Retinopathy and Macular Edema Using Ultra-Widefield Fundus Imaging](https://arxiv.org/abs/2409.12854)

*🤝 Contributing*
Contributions are welcome! Please open an issue or submit a pull request for any improvements.

*📧 Contact*
For any queries, feel free to reach out at sunilkumar.a@ihub-data.iiit.ac.in
-seaborn
-opencv-python
-scikit-learn



