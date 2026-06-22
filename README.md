<img width="918" height="914" alt="c630fcc659427ac1691fb7e1c7d58898" src="https://github.com/user-attachments/assets/4c653dfb-fa5e-4faf-8186-0d01614b1fdf" />GFBA-Net
=
Accurate medical image segmentation serves as a crucial foundation for computer-aided diagnosis and precision medicine. However, medical images generally suffer from blurred boundaries and low contrast; conventional encoder-decoder networks tend to lose spatial details during continuous downsampling, while successive upsampling often leads to information degradation. These issues make it difficult to precisely delineate the fine-grained boundaries between target regions and surrounding tissues. To address these challenges, we propose a Geometric Feature-driven Boundary-aware Network (GFBA-Net) tailored for complex medical image segmentation tasks. This network explicitly models boundary information through gradient and curvature geometric features and embeds them into both the encoding and decoding processes, thereby effectively mitigating feature attenuation and enhancing the model's boundary perception capability. Specifically, during the encoding stage, the network extracts geometric features from the raw image via the Geometric Feature Extractor (GFE). Concurrently, the Bidirectional Boundary Guidance (BBG) module is proposed to strengthen the boundary representations. In the decoding stage, the Boundary-Guided Channel-Spatial Fusion (BCSF) module incorporates the GFE to supplement the detail information lost after decoder upsampling. Extensive experiments on five public datasets (ISIC2017, FIVES, BUSI, COVID-19, and PH2) demonstrate that GFBA-Net outperforms other mainstream models in key metrics, including Dice, HD95 and IoU.

## Model
![Uploading c630fcc659427ac1691fb7e1c7d58898.png…]()


## Datasets
Tested on 5 medical image segmentation datasets:

1. ISIC2017 (Skin Lesion)
1. FIVES (Eye Vessels)
1. BUSI (Breast Ultrasound)
1. COVID-19 (Lung CT)
1. PH2 (Dermoscopy)

## Setup
```java
conda create -n GFBANet python=3.8
conda activate GFBANet
conda install pytorch==1.13.1 torchvision==0.14.1 torchaudio==0.13.1 pytorch-cuda=11.7 -c pytorch -c nvidia
pip install numpy opencv-python pillow scikit-learn matplotlib thop tqdm tensorboard joblib
```

## Dataset Structure
```java
data/
├── FIVES/
│   ├── train/
│   │   ├── images/
│   │   └── masks/
│   ├── val/
│   │   ├── images/
│   │   └── masks/
│   └── test/
│       ├── images/
│       └── masks/
└── ... (other datasets)
```

## Usage
1. Activate Environment
```java
conda activates GFBANet
cd ./project
```
1. train：
```java
python train.py
```
1. test：
```java
python test.py
```

## Parameters

1.epoch:2000
1.Learning rate: 1e-3
1.Batch size: 16
1.Early stopping patience: 100
1.Weight decay: 1e-5






