# Large-scale Unsupervised Semantic Segmentation

This is a Large-scale Unsupervised Semantic Segmentation benchmark.

![sample_vis](https://user-images.githubusercontent.com/20515144/149650063-cd28c7aa-2062-4379-a326-4dcd593495a5.jpg)

# Introduction

Powered by the ImageNet dataset, unsupervised learning on large-scale data has made significant advances for classification tasks. There are two major challenges to allowing such an attractive learning modality for segmentation tasks: i) a large-scale benchmark for assessing algorithms is missing; ii) unsupervised shape representation learning is difficult. We propose a new problem of large-scale unsupervised semantic segmentation (LUSS) with a newly created benchmark dataset to track the research progress. Based on the
ImageNet dataset, we propose the ImageNet-S dataset with 1.2 million training images and 50k high-quality semantic segmentation annotations for evaluation. Our benchmark has a high data diversity and a clear task objective. We also present a simple yet effective baseline method that works surprisingly well for LUSS. In addition, we benchmark related un/weakly/fully supervised methods accordingly, identifying the challenges and possible directions of LUSS.

# ImageNet-S dataset [Download Link](https://github.com/UnsupervisedSemanticSegmentation/ImageNet-S)

The ImageNet-S dataset contains 1183322 training, 12419 validation, and 27423 testing images from 919 categories. We annotate 39842 val/test images and 9190 training images with precise pixel-level masks.

| Dataset | category | train   | val   | test  |
|------------------|----------|---------|-------|-------|
| ImageNet-S_{50}  | 50       | 64431   | 752   | 1682  |
| ImageNet-S_{300} | 300      | 384862  | 4097  | 9088  |
| ImageNet-S        | 919      | 1183322 | 12419 | 27423 |

# Online benchmark
* Fully unsupervised protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1317)
* Distance matching protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1315)
* Semi-supervised protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1318)
* Free protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1316)

Due to the lack of ground-truth (GT) category labels during training, 
LUSS models cannot be directly evaluated like in the supervised setting.
We present three evaluation protocols for LUSS, including the fully unsupervised evaluation, 
semi-supervised evaluation, and distance matching evaluation.
To explore the upper bound of ImageNet-S semantic segmentation, 
we also present a free evaluation benchmark with no limitaion.

## Submission rules

The submission file has the following structure:

```
├── submission.zip
    ├── n...                              // prediction
    ├── n...                              // prediction
    ├── n...                              // prediction
    ├── match.json                        // optional
    └── method.txt                        // description of method
```

**[submission example]()**

You must submit your results to the corresponding protocols, and **miss-matched submissions will be deleted**.
We summarize a table for different protocols:

|      Actions          | Fully unsupervised | Distance matching | Semi-supervised | Free |
|:---------------------:|--------------------|-------------------|-----------------|------|
| ImageNet-S~{50/300/full} only^{note1}   |     ✓                |     ✓   |     ✓          |      |
| Only unsupervised pre-training   |                    |        ✓            |                 |      |
| Label generation and fine-tuning         |        ✓             |                    |                 |      |
| Fine-tune with 1% training image annotation   |                    |                   |       ✓            |      |
| Supervised pre-trained weights? |                    |                   |                 | ✓    |
| Extra training data?  |                    |                   |                 |    ✓   |
| Supervised edge/saliency?  |                    |                   |                 |    ✓   |

Note1: Pre-training on the ImageNet-S~{full} and fine-tuning on the ImageNet~{300/50} is not allowed.

## Fully unsupervised protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1317)

The fully unsupervised evaluation protocol requires no human-annotated labels during training and only needs the validation/test set for evaluation. Unlike the supervised tasks, categories are generated by the model in the LUSS task, which needs to match with GT categories during evaluation. 
We present the default image-level matching scheme in the [ImageNet-S toolbox](https://github.com/UnsupervisedSemanticSegmentation/ImageNet-S), 
while an effective matching scheme should improve LUSS evaluation performance.
You need to match the generated categories with GT categories, and assign matched categories to the test images.

## Distance matching protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1315)

In distance matching evaluation protocol, 
we directly get the embeddings of GT categories with
the pixel-level labeled training images
and match them with embeddings in validation/testing set to assign labels.
You don't need to care about the label generation in LUSS and only need to provide a unsupervised pre-trained model.
The inference code for distance matching is in the  [ImageNet-S toolbox](https://github.com/UnsupervisedSemanticSegmentation/ImageNet-S).   

## Semi-supervised protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1318)

We can conduct semi-supervised fine-tuning to evaluate LUSS models
as we annotate about 1% of training images with pixel-level labels.
The semi-supervised evaluation protocol requires fine-tuning the trained LUSS models
with the 1% pixel-level human-labeled training images.
Therefore, this protocol does not need matching generated and GT category.
Also, this protocol is suitable for real-world applications where
a small part of images are human-labeled and many images are unlabeled.

## Free protocol [link](https://codalab.lisn.upsaclay.fr/competitions/1316)

In this protocol, you can do whatever you want to improve the semantic segmentation performance on ImageNet-S, 
e.g. ImageNet-21K supervised pretraining, image-level annotations, and pixel-level annotations.
The only rule is donot use image-level or pixel-level annotations of val/test sets.

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
