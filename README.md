# DFFR: DETR with Foreground-Guided Feature Refinement Network for End-to-End Underwater Object Detection

<p align="center">
Authors
</p>

## Detection Results Demo
Here is a demonstration of our DFFR model performing real underwater object detection:
**Video demonstration:**  
Link: [Baidu Drive Download](https://pan.baidu.com/s/1G1JkQDLwrHmQ2SlqFAGWuQ)  
Extraction code: `23uq`





## Introduction
Underwater object detection plays a vital role in marine resource exploration, autonomous underwater vehicles, and environmental monitoring. Compared to land scenarios, underwater object detection often suffers from low contrast, object occlusion, and blurring, which severely degrade detection performance. To effectively address these issues, we propose the DETR with Foreground-Guided Feature Refinement Network (DFFR). We first adopt lightweight HGNetV2 to extract multi-scale deep semantic features. To further enhance semantic feature representation, we integrate image and textual information using cross-modality encoder. We then propose the Foreground-Guided Feature Refinement (FFR) module, which enables inter-layer feature fusion through high-level contextual guidance to effectively improve foreground recognition. Meanwhile, we propose the Location Perception Fusion (LPF) strategy, which integrates multi-scale features to improve feature consistency and discriminative capability. Finally, we pass the refined features through the Fine-grained Distribution Refinement (FDR) module to achieve iterative optimization of the output distribution. 
Comprehensive experimental results demonstrate that DFFR outperforms existing state-of-the-art methods in multiple metrics, including AP, AP$_{\mathrm{50}}$, and AP$_{\mathrm{75}}$, with improvements in AP of 2.1\%, 2.9\%, respectively on two underwater benchmark datasets, and AP$_{\mathrm{50}}$ of improvement of 0.3\% on the COCO dataset.

![pipeline](./img/Overall%20flowchart.png)

## Dependencies

- Python == 3.7.11
- PyTorch >= 2.0.1
- torchvision >= 0.15.2
- faster-coco-eval >= 1.6.5
- PyYAML
- tensorboard
- scipy
- calflops
- transformers
- loguru
- mmdetection == 2.22.0

Our experiment were executed on a PC equipped with an Intel Core i7-12700KF CPU, 32 GB of system memory, and an NVIDIA GeForce 4060 Ti GPU with 32 GB of video memory.
## Datasets

**DUO**: https://github.com/chongweiliu/DUO


Other underwater datasets: https://github.com/mousecpn/Collection-of-Underwater-Object-Detection-Dataset

download COCO2017 from [OpenDataLab](https://opendatalab.com/OpenDataLab/COCO_2017) or [COCO](https://cocodataset.org/#download).
After downloading all datasets, create CIDNet document.

It is recommended to symlink the dataset root to `$data`.

```
CIDNet
├── data
│   ├── DUO
│   │   ├── annotaions
│   │   ├── train2017
│   │   ├── test2017
│   ├── COCO
│   │   ├── annotaions
│   │   ├── train2017
│   │   ├── val2017
│   ├── UTDAC
│   │   ├── annotaions
│   │   ├── train2017
│   │   ├── val2017
```


## Train

```
We provide multiple training strategies for users to choose from, offering flexibility for different application scenarios.
$ python train.py -c configs/DFFR/DFFR_hgnetv2_duo.yml --use-amp --seed=0 --device cuda:0
```
## Checkpoint
```
The trained weights for our DFFR model can be downloaded here:

- **DUO dataset**: [Download Link](https://pan.baidu.com/s/1_TVF-OcJ2BqFGs5cooeVVA)  
  **Extraction Code**: `kksq`
 ```

## Results

![pipeline](./img/Main%20results.png)



## Acknowledgement



## Citation



