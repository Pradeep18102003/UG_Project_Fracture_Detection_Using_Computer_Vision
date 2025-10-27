# Rock Fracture Detection using U-Net

This repository contains a deep learning project for identifying rock fractures in geological outcrops. The project uses a **U-Net architecture** implemented in PyTorch to perform semantic segmentation, accurately predicting and generating binary masks for fracture edges in rock images.

This tool is valuable for applications in geoscience, geoengineering, and structural geology, where characterizing fracture networks is a key component of analysis.

## Model Results

The trained U-Net model successfully identifies complex fracture patterns on new images. The model was trained for 5 epochs, achieving a final validation **Dice score of 0.8379**.

Here is an example of the model's prediction on a test image sourced from the internet [from: Test_for_Rock_Fracture.ipynb]:

## Model Results

<img width="1125" height="289" alt="image" src="https://github.com/user-attachments/assets/6ebcf8df-98fe-4302-ae27-ef0ff504b547" />


## Dataset

[cite_start]This model was trained on the **GeoCrack** dataset, which is a high-resolution, open-source annotated dataset of fracture traces from geological outcrops[cite: 7].

* **Source:** The dataset was developed by researchers and is detailed in the accompanying paper. [cite_start]It contains 12,158 image-mask pairs ($224 \times 224$ pixels) derived from photogrammetric surveys at 11 sites across Europe and the Middle East[cite: 10, 89].
* **Methodology:** For a complete overview of the data collection, annotation, and vetting process, please see the PDF file in this repository:
    [cite_start]`Data/data_collection_methodology/GeoCrack A High-Resolution Dataset...pdf` [cite: 104]

## Methodology

The project is contained in two main Jupyter notebooks:

1.  **`rock_fracture_detection_ugp.ipynb` (Training):** This notebook covers the complete data preparation and training pipeline.
    * **Data Loading:** Loads the original images and their corresponding binary masks [from: rock_fracture_detection_ugp.ipynb].
    * **Patching:** Implements a "smart patch retention" algorithm. It creates $224 \times 224$ patches and discards any patches where the mask has less than a 1% white pixel (fracture) ratio [from: rock_fracture_detection_ugp.ipynb].
    * **Data Split:** Splits the resulting 12,158 patches into training (50%), validation (25%), and test (25%) sets, matching the split used in the GeoCrack paper.
    * **Model:** Defines a standard U-Net architecture using PyTorch [from: rock_fracture_detection_ugp.ipynb].
    * **Training:** Trains the model for 5 epochs using a `BCEWithLogitsLoss` function and the Adam optimizer [from: rock_fracture_detection_ugp.ipynb].

2.  **`Test_for_Rock_Fracture.ipynb` (Inference):** This notebook demonstrates how to use the trained model for prediction.
    * Loads the saved model weights (`unet_model.pth`) [from: Test_for_Rock_Fracture.ipynb].
    * Fetches and preprocesses a new sample image from a URL [from: Test_for_Rock_Fracture.ipynb].
    * Runs the model to generate a predicted probability map and a final binary mask (thresholded at 0.5) [from: Test_for_Rock_Fracture.ipynb].
    * Visualizes the original image, the probability map, and the final mask side-by-side [from: Test_for_Rock_Fracture.ipynb].

## **Repository Structure**
```
📂 Rock_Fracture_Detection
│── 📂 notebook
│   └── rock_fracture_detection_ugp.ipynb  # Model Training
|   └── Test_for_Rock_Fracture.ipynb   # Testing the model on images from internet
│── README.md  # Project documentation
│── requirements.txt  # Dependencies (if needed)
```

## How to Use

### 1. Training the Model

The training was performed on Kaggle to utilize its free GPU resources.

1.  [cite_start]**Get the Data:** Download the [GeoCrack Dataset](https://doi.org/10.7910/DVN/E4OXHQ)[cite: 272].
2.  **Set up Environment:** Upload the `rock_fracture_detection_ugp.ipynb` notebook to Kaggle (or any environment with PyTorch and a GPU).
3.  **Configure Paths:** Adjust the data paths in the notebook to point to your dataset location [from: rock_fracture_detection_ugp.ipynb].
4.  **Run:** Execute all cells in the notebook. The trained model will be saved as `unet_model.pth` [from: rock_fracture_detection_ugp.ipynb].

### 2. Testing on a New Image

1.  **Get the Model:** Ensure you have the saved `unet_model.pth` file in the same directory as the `Test_for_Rock_Fracture.ipynb` notebook [from: Test_for_Rock_Fracture.ipynb].
2.  **Run:** Open and run all cells in the `Test_for_Rock_Fracture.ipynb` notebook.
3.  **Test Your Own:** You can change the `IMAGE_URL` variable in the notebook to test any rock image from the internet [from: Test_for_Rock_Fracture.ipynb].

## Implementation Details

* This project is implemented in **PyTorch** [from: rock_fracture_detection_ugp.ipynb].
* The code is contained entirely within Jupyter Notebooks to facilitate easy execution on cloud-based GPU platforms like Kaggle or Google Colab, which was a priority due to local computational limitations.

## Acknowledgements

This project was made possible by the authors of the GeoCrack dataset. Full citation:

> Yaqoob, M., Ishaq, M., Ansari, M.Y. et al. GeoCrack: A High-Resolution Dataset For Segmentation of Fracture Edges in Geological Outcrops. [cite_start]*Sci Data* 11, 1318 (2024). https://doi.org/10.1038/s41597-024-04107-0 [cite: 1, 3, 5, 25]


## License
This project is licensed under the [MIT License](LICENSE).

## 📧 Contact
- If you have any questions or feedback, feel free to reach out via email: pradeep18kumar10@gmail.com  
- LinkedIn: [Pradeep Kumar](https://www.linkedin.com/in/pradeep-kumar-bba090320/)

