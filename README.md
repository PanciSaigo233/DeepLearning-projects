# DeepLearning-projects

Deep learning projects developed for the **Artificial Neural Networks and Deep Learning (AN2DL)** course at **Politecnico di Milano** (Academic Year 2024–2025).

This repository contains two team assignments exploring computer vision through **image classification** and **semantic segmentation**. Our work covers exploratory data analysis, data cleaning, augmentation, architecture design, transfer learning, model optimization, and experimental evaluation.

## Projects at a Glance

| Project | Task | Main approaches | Best reported test result |
| --- | --- | --- | --- |
| **Homework 1: Blood Cell Classification** | Classify 96 × 96 RGB images into 8 blood-cell categories | Custom CNNs, transfer learning, VGG16 fine-tuning, data augmentation | **67% accuracy** |
| **Homework 2: Mars Terrain Segmentation** | Assign one of 5 terrain labels to each pixel of a 64 × 128 grayscale image | U-Net, ASPP, attention gates, deep supervision, combined losses | **61.79% mean IoU** |

> **Note:** Test scores are taken from the accompanying project reports. Validation scores are reported separately and should not be interpreted as held-out test results.

## Homework 1 — Blood Cell Image Classification

**Goal:** Build a multiclass image classifier that assigns blood-cell images to one of eight categories.

### Methodology

- Analyzed class imbalance and removed irrelevant or anomalous images.
- Normalized image intensities and compared training/validation splits.
- Trained a convolutional neural network from scratch, experimenting with regularization, dropout, pooling, and activation functions.
- Investigated augmentation strategies, including **AugMix, MixUp, RandomAugment, CutMix, and GridMask**.
- Compared pretrained **VGG16, ResNet50V2, InceptionV3, MobileNet, EfficientNetB0, and EfficientNetB2** models.
- Fine-tuned VGG16 with an adapted classification head, normalization, dropout, and learning-rate adjustments.

### Reported results

| Model | Validation accuracy |
| --- | ---: |
| **VGG16** | **96.32%** |
| ResNet50V2 | 96.15% |
| InceptionV3 | 93.48% |
| EfficientNetB0 | 45.40% |
| EfficientNetB2 | 42.31% |

The final VGG16 approach reached a **reported test accuracy of 67%**. The gap between validation and test performance was an important finding, highlighting challenges with overfitting and generalization.

**Files:** `Homework_1_Minimal_Working_Exampl_TeamRookie.ipynb` and `AN2DL_Homeworks_Report_Team_Rookie.pdf`.

## Homework 2 — Mars Terrain Semantic Segmentation

**Goal:** Perform pixel-wise classification of grayscale Mars terrain images into five terrain classes.

### Methodology

- Cleaned the dataset and examined pixel-level class imbalance.
- Developed a **U-Net baseline** with encoder–decoder blocks and skip connections.
- Explored geometric and photometric augmentation, including flips, rotations, brightness, and contrast adjustments.
- Evaluated **Dice, Focal, Boundary, and weighted Cross-Entropy losses**, as well as combined-loss strategies.
- Added **Atrous Spatial Pyramid Pooling (ASPP)** for multiscale contextual information.
- Integrated **attention gates** into skip connections, and explored additional spatial/channel attention, Transformer blocks, and sub-pixel upsampling.
- Applied **deep supervision** to intermediate decoder outputs to support multiscale learning.

### Reported progression

| Experiment | Test mean IoU |
| --- | ---: |
| Basic U-Net baseline | 11.75% |
| Improved augmentation | 46.48% |
| ASPP | 49.44% |
| Attention gates | 51.60% |
| **Deep supervision (final approach)** | **61.79%** |

The final configuration combined **attention gates, ASPP, deep supervision, and dynamic augmentation**. The results also showed that simply increasing U-Net depth or model complexity did not consistently improve performance.

**Files:** `Homework2_final_version_Team Rookie.ipynb` and `AN2DL_Homework_2_Report_FinalVersion.pdf` (the notebook and report may be stored inside the uploaded Homework 2 ZIP archive).

## Technologies and Concepts

- **Python** and **Jupyter Notebook / Google Colab**
- **TensorFlow / Keras**, NumPy, and computer vision preprocessing utilities
- Convolutional neural networks and pretrained backbone architectures
- Transfer learning and fine-tuning
- U-Net-based semantic segmentation
- Data augmentation, regularization, attention mechanisms, and deep supervision
- Evaluation with classification accuracy, confusion matrices, and mean Intersection over Union (mIoU)

## Getting Started

1. Clone this repository and open the notebook for the project you want to explore.
2. Use a compatible Python environment with the libraries imported in that notebook. The notebooks were developed for **Google Colab**, so some cells reference Google Drive paths.
3. Obtain the corresponding course dataset separately; the datasets are **not assumed to be included** in this repository.
4. Update data paths, output directories, and any Colab-specific setup cells to match your environment.
5. Run the notebook sections in order to preprocess the data, train/evaluate models, and inspect results.

> These are research/coursework notebooks rather than a packaged, one-command training pipeline. Reproducing the reported results may require the original datasets, compatible package versions, and access to the relevant evaluation platform.

## Team

**Team Rookie**

- Jiaxiang Yi
- Yang Hao Mao
- Simona Cai
- Ying Zhou

## Acknowledgments

Developed as part of the **Artificial Neural Networks and Deep Learning** course at **Politecnico di Milano** in 2024–2025.

For implementation details, experimental decisions, and discussion of limitations, see the notebooks and their accompanying reports.
