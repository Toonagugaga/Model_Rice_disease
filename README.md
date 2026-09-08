[ININE_Model_README.md](https://github.com/user-attachments/files/31939625/ININE_Model_README.md)
# I'Nine - Rice Disease Detection Model

## Overview
This AI model is designed for detecting and classifying rice diseases from photographs of rice leaves and other parts of the rice plant. The project utilizes the **YOLOv26L** architecture, which offers real-time processing capabilities and high accuracy in object detection, quickly drawing boundaries around lesions.

## Dataset
The training dataset was collected from the Department of Rice and the Kaggle platform.
- **Total number of images:** 2,105 images
- **Image size:** 800 x 800 pixels
- **Annotation:** Uses **Polygon Labeling** to draw borders closely aligned with lesions. This helps reduce background noise better than typical Bounding Box patterns.
- **Data Set Division:**
- Training Set: 80%
- Validation Set: 10%
- Testing Set: 10%
- **Data Augmentation:** Uses image rotation and flipping techniques to increase variety and reduce overfitting.

### Rice Disease Classes (9 Classes)
1. `Bacterial_Blight` (Rice Leaf Blight)
2. `Brown_Spot` (Brown Leaf Spot)
3. `Rice_Blast` (Rice Blast)
4. `Narrow_Brown_Spot` (Narrow Brown Leaf Spot)
5. `False_Smut` (False Smut)
6. `Dirty_Seed` (Dirty Seed)
7. `Sheath_Rot` (Sheath Rot) (Sheath Rot)
8. Stem Rot (Stem Rot)
9. Red Stripe (Red Stripe Disease)

## Environment and Hyperparameters
- **Architecture:** YOLOv26L (Pre-trained weights)
- **Training Hardware:** GPU Tesla T4 x 2 (on Kaggle Notebook)
- **Number of Epochs:** 100 epochs (Patience set = 20 for Early Stopping)
- **Batch Size:** 16
- **Optimizer:** Auto
- **Seed:** 0

## Model Performance
Testing showed that the model using polygon labeling performed best at **95 Epochs** before reaching saturation. (Convergence)
- **Precision:** 0.8773
- **Recall:** 0.7185
- **Harmonic Mean (F1-Score):** 0.7900
- **Average Accuracy (mAP50):** 0.8077
- 
## Model Limitations
- **Class Imbalance Problem:** Diseases with limited training images (e.g., red stripe disease, stem rot) will have poor predictive performance.
- **False Negatives:** The model may miss small and widely distributed lesions, such as seed variegation and brown spot disease.
- Cross-class false positives are rare; the model has a very good ability to differentiate between disease types.
