## Large-scale Unsupervised Semantic Segmentation

This is a Large-scale Unsupervised Semantic Segmentation benchmark.

![sample_vis](https://user-images.githubusercontent.com/20515144/149650063-cd28c7aa-2062-4379-a326-4dcd593495a5.jpg)

### Introduction
Powered by the ImageNet dataset, unsupervised learning on large-scale data has made significant advances for classification tasks. There are two major challenges to allowing such an attractive learning modality for segmentation tasks: i) a large-scale benchmark for assessing algorithms is missing; ii) unsupervised shape representation learning is difficult. We propose a new problem of large-scale unsupervised semantic segmentation (LUSS) with a newly created benchmark dataset to track the research progress. Based on the
ImageNet dataset, we propose the ImageNet-S dataset with 1.2 million training images and 50k high-quality semantic segmentation annotations for evaluation. Our benchmark has a high data diversity and a clear task objective. We also present a simple yet effective baseline method that works surprisingly well for LUSS. In addition, we benchmark related un/weakly/fully supervised methods accordingly, identifying the challenges and possible directions of LUSS.

### ImageNet-S dataset
The ImageNet-S dataset contains 1183322 training, 12419 validation, and 27423 testing images from 919 categories. We annotate 39842 val/test images and 9190 training images with precise pixel-level masks.

| Dataset | category | train   | val   | test  |
|------------------|----------|---------|-------|-------|
| ImageNet-S_{50}  | 50       | 64431   | 752   | 1682  |
| ImageNet-S_{300} | 300      | 384862  | 4097  | 9088  |
| ImageNet-S        | 919      | 1183322 | 12419 | 27423 |


[ImageNet-S Download Link](https://github.com/UnsupervisedSemanticSegmentation/ImageNet-S)

### Online benchmark

Coming soon.

### Citation
```
@article{gao2021luss,
  title={Large-scale Unsupervised Semantic Segmentation},
  author={Gao, Shanghua and Li, Zhong-Yu and Yang, Ming-Hsuan and Cheng, Ming-Ming and Han, Junwei and Torr, Philip},
  journal={arXiv preprint arXiv:2106.03149},
  year={2021}
}
```

### Support or Contact

If you have any questions, feel free to E-mail me via: shgao(at)live.com
