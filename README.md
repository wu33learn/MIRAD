# MIRAD - A comprehensive real-world robust anomaly detection dataset for Mass Individualization

Pulin Li, Guocheng Wu, Yanjie Zhou, Yuxin Zheng, Wei Zhang.

## Table of Contents
* [Introduction](#introduction)
* [Data description](#data-description)
* [Data download](#data-download)
* [Data preparation](#data-preparation)
* [Metric computation](#metric-computation)
* [Citation](#citation)
* [License](#license)

## Introduction
This repository contains the resources for our paper ["MIRAD - A comprehensive real-world robust anomaly detection dataset for Mass Individualization"](https://arxiv.org/pdf/2207.14315.pdf). MIRAD represents a hybrid scenario bridging single class and multi class anomaly detection paradigms. Currently we release the Mass Individualization Robust Anomal Detection (MIRAD) dataset. 
![](figures/new_challenges.png)


## Data description
![](figures/individualized_products.png)

MIRAD, comprising 10 categories of individualized products, encompasses three design paradigms, including geometrically complex components (Geometric Blocks, Buttons), numerically and symbolically encoded items (Number Blocks with Arabic numerals, mathematical symbols), and stylized artifacts (Rabbit Pendants, Magnetic Bookmarks). Each product category offers diverse options in color, shape, pattern, and size, covering one or even all three design paradigms.It specifically incorporates multi-object inspection scenarios where two or more individualized products coexist within single frames. The MIRAD dataset comprises 2398 defect-free training images and 2391 test samples, with 1737 test images containing pixel-level annotated defects. Distributed production nodes employ diverse motion and illumination strategies, different camera specifications , and node-specific background, collectively mirroring the diversity of real-world dis manufacturing networks. Both surface defects and logical flaws are captured under node-specific imaging conditions.
The MIRAD dataset bridges the gap between laboratory research and practical quality control in mass individualization under the context of social manufacturing. 

### Individualized designs
![](figures/Individualized_designs_and_defect.png)
### Statistical overview
![](figures/Statistical_overview.png)


## Data download

We host the MIRAD dataset in AWS S3 and you can download it by this [URL](https://drive.google.com/file/d/1-4aMEtiTvk77Oo-oNW6WdPPuxpfHRKwq/view?usp=sharing). 

The data tree of the downloaded data is as follows.
```shell
MIRAD
|-- building_block
|-----|--- train
|-----|-----|----- good
|-----|--- test
|-----|-----|----- good
|-----|-----|----- anomaly
|-----|--- ground_truth
|-- chain_buckle
|-----|----- ...
```

 
## Experimental results
Based on MIRAD, we explore how existing anomaly detection models perform when confronted with the individualized products, as well as their robustness to imaging heterogeneity across distributed production nodes. Specially, we evaluate three kinds of approaches on MIRAD dataset, including single-class, multi-class and zero-shot detection models, providing a foundation for future analyses.
### single and multi-class approches
![](figures/single_multi.png)
Performance on the MIRAD dataset reveals notable limitations. Single-class methods achieved only 76.2% I-AUROC, whereas multi-class approaches scored an even lower score of 71.1%. In contrast, both single-class and multi-class frameworks reached approximately 98% I-AUROC on MVTec AD and around 93% on VisA. This significant performance drop highlights the increased difficulty of defect detection in social manufacturing settings. 


### zero-shot approaches
![](figures/zero.png)
Although AnomalyCLIP (Zhou et al., 2024) and AdaCLIP (Cao et al., 2024) have been pre-trained on auxiliary datasets such as MVTec AD(Bergmann et al., 2019) and VisA (Zou et al., 2022), they still fell short on the MIRAD benchmark. The unified representations of normality and abnormality learned from conventional datasets may fail to generalize to MIRAD, where individualized normal features vary widely across instances. Consequently, MIRAD emerges as a valuable counterpart to traditional mass-production benchmarks, more accurately reflecting the complexities of decentralized, individualized manufacturing.

## 

## Citation
Please cite the following paper if this dataset helps your project:

```bibtex
@article{zou2022spot,
  title={MIRAD - A comprehensive real-world robust anomaly detection dataset for Mass Individualization},
  author={Zou, Yang and Jeong, Jongheon and Pemula, Latha and Zhang, Dongqing and Dabeer, Onkar},
  journal={arXiv preprint arXiv:2207.14315},
  year={2022}
}
```

## License
The data is released under the CC BY 4.0 license.
