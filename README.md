# Large-scale Unsupervised Semantic Segmentation

This is a Large-scale Unsupervised Semantic Segmentation benchmark.

![sample_vis](https://user-images.githubusercontent.com/20515144/149650063-cd28c7aa-2062-4379-a326-4dcd593495a5.jpg)

# Introduction

Powered by the ImageNet dataset, unsupervised learning on large-scale data has made significant advances for classification tasks. There are two major challenges to allowing such an attractive learning modality for segmentation tasks: i) a large-scale benchmark for assessing algorithms is missing; ii) unsupervised shape representation learning is difficult. We propose a new problem of large-scale unsupervised semantic segmentation (LUSS) with a newly created benchmark dataset to track the research progress. Based on the
ImageNet dataset, we propose the ImageNet-S dataset with 1.2 million training images and 50k high-quality semantic segmentation annotations for evaluation. Our benchmark has a high data diversity and a clear task objective. We also present a simple yet effective baseline method that works surprisingly well for LUSS. In addition, we benchmark related un/weakly/fully supervised methods accordingly, identifying the challenges and possible directions of LUSS.

# Applications and Sourcecodes

## Unsupervised semantic segmentation
The Large-scale Unsupervised Semantic Segmentation (LUSS)
task aims to assign labels from hundreds of categories to pixels from
millions of images without the help of human annotation. The model
learns to conduct semantic segmentation with Self-Learning.

[PASS](https://github.com/LUSSeg/PASS): A new method for LUSS.

## Semi-supervised semantic segmentation
Semi-supervised semantic segmentation task aims
to finetuning on the pretrained models with 1% pixel-level annotations
in ImageNet-S dataset to support large-scale semantic segmentation.
You can use it to benchmark pretraining strategies or network designs.

[ImageNetSegModel](https://github.com/LUSSeg/ImageNetSegModel): A semi-supervised codebase to test various self-supervised pretraining models and backbones.

[MMSegmentaion](https://github.com/LUSSeg/mmsegmentation/tree/imagenets/configs/imagenets): The large-scale semantic segmentation on the MMSegmentation codebase, better performance is observed thanks to the MMSegmentation.
# ImageNet-S dataset 
Based on the ImageNet dataset, the ImageNet-S dataset has 1.2 million training images and 50k high-quality semantic segmentation annotations to support unsupervised/semi-supervised semantic segmentation on the ImageNet dataset.
It contains 1183322 training, 12419 validation, and 27423 testing images from 919 categories. We annotate 39842 val/test images and 9190 training images with precise pixel-level masks.

[**Download Link**](https://github.com/LUSSeg/ImageNet-S#imagenet-s-dataset-preparation)

[**Dataset Information**](https://github.com/LUSSeg/ImageNet-S#dataset-information)

# Online benchmark
Due to the lack of ground-truth (GT) category labels during training, 
LUSS models cannot be directly evaluated like in the supervised setting.
We present three evaluation protocols for LUSS, including the fully unsupervised evaluation, 
semi-supervised evaluation, and distance matching evaluation.
To explore the upper bound of ImageNet-S semantic segmentation, 
we also present a free evaluation benchmark with no limitaion.

[**Submission guidance**](https://github.com/LUSSeg/ImageNet-S#online-benchmark)
*  [Fully unsupervised protocol](https://codalab.lisn.upsaclay.fr/competitions/1317)
*  [Distance matching protocol](https://codalab.lisn.upsaclay.fr/competitions/1315)
*  [Semi-supervised protocol](https://codalab.lisn.upsaclay.fr/competitions/1318)
*  [Free protocol](https://codalab.lisn.upsaclay.fr/competitions/1316)

# Citation

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
