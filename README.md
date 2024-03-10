# **APEDIA**: **A**ngiosarcoma **P**D-L1 **E**xpression **DIA**gnostics with Deep Learning

APEDIA utilizes deep learning to enhance the decision quality of pathologists in the assessment of PD-L1 expression in angiosarcoma. Given a whole-slide image, it calculates the Tumor Proportion Score, which indicates the percentate of tumor cells which are PD-L1 positive.

**Note**: This repository is currently under construction. More features and documentation will be added as the project progresses.

## Scripts in the Repository

The APEDIA project includes a series of scripts designed to preprocess data, train models, and predict scores relevant to PD-L1 expression in angiosarcoma. Below is a brief overview of each script and its purpose.

### Training Scripts

1. **Tumor Patch Detector Training**
   - **Script Name**: `train_tumor_patch_detector.py`
   - **Description**: Trains a model to detect tumor patches in WSIs.

2. **Cell Type Detector Training**
   - **Script Name**: `train_cell_type_detector.py`
   - **Description**: Trains a model to differentiate between PD-L1 positive tumor cells, PD-L1 negative tumor cells, and other cells within tumor patches.

### Preprocessing Script

- **Preprocess Data for Cell Type Detection Training**
  - **Script Name**: `preprocess_cell_type_data.py`
  - **Description**: Leverages trained generalist models to transform sparse cell type annotations into annotations suitable for training. *Cellpose* is used to identify cell instances and outline the nuclei, eliminating the need for manual annotation of each cell's outline. A *DeepLIIF* generative adverserial network is employed to isolate the hema components from heavily PD-L1 stained areas, thereby enhancing Cellpose's precision in identifying cell instances. This preprocessing step is required for preparing the dataset for accurate cell type detection training.

### Prediction Script

- **Predict Tumor Proportion Score (TPS) for WSIs**
  - **Script Name**: `predict_tps_wsi.py`
  - **Description**: Predicts the Tumor Proportion Score for a whole-slide image, integrating outputs from both the tumor patch and cell type detection model to provide a comprehensive PD-L1 expression score. 

## Getting Started

TODO

## License

TODO
