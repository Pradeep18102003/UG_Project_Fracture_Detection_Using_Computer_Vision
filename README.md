# UG_Project_Fracture_Detection_Using_Computer_Vision

## **Overview**
This repository contains a Jupyter Notebook that implements a deep learning approach to detect and segment rock fractures using the U-Net architecture. The project is designed to assist geological studies by automating fracture identification in geological outcrops.

## **Project Structure**
```
📂 Rock_Fracture_Detection
│── 📂 notebook
│   └── Rock_fracture_detection.ipynb  # Main implementation
│── README.md  # Project documentation
│── requirements.txt  # Dependencies (if needed)
```

## **Dataset**
- **Dataset Name:** GeoCrack – A High-Resolution Dataset for Fracture Segmentation
- **Total Images:** 12,000 high-resolution images
- **Training Subset Used:** 200 images (due to computational limitations)
- **Testing Subset Used:** 20 images
- **Annotations:** Expert-labeled pixel-wise segmentation masks

## **Model Details**
- **Architecture:** U-Net (CNN-based segmentation model)
- **Preprocessing:** Image resizing, normalization, and augmentation
- **Training Setup:**
  - Optimizer: Adam
  - Loss Function: Dice Loss + Binary Cross-Entropy
  - Metrics: IoU Score, Dice Coefficient

## **Usage**
### **1. Clone the Repository**
```bash
git clone https://github.com/yourusername/rock-fracture-detection.git
cd rock-fracture-detection
```

### **2. Open the Notebook**
Run the Jupyter Notebook to train and test the model:
```bash
jupyter notebook notebook/Rock_fracture_detection.ipynb
```

### **3. Modify and Experiment**
- Update the dataset path inside the notebook.
- Modify hyperparameters as needed.
- Run inference on new images by modifying the test cell.

## **Future Work**
- Train on the full dataset using Kaggle or Google Colab’s free GPUs.
- Improve model performance through fine-tuning.
- Experiment with advanced segmentation models such as DeepLabV3 or Mask R-CNN.


## **Contact**
## 📧 Contact
- If you have any questions or feedback, feel free to reach out via email: pradeep18kumar10@gmail.com  
- LinkedIn: [Pradeep Kumar](https://www.linkedin.com/in/pradeep-kumar-bba090320/)

