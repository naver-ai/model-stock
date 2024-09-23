<div align="center">

# Model Stock: All we need is just a few fine-tuned models

**[Dong-Hwan Jang](https://donghwanjang.github.io), [Sangdoo Yun](https://sangdooyun.github.io/), [Dongyoon Han](https://sites.google.com/site/dyhan0920/)** <br>

[NAVER AI Lab](https://naver-career.gitbook.io/en/teams/clova-cic/ai-lab)

[![CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://github.com/naver-ai/augsub/blob/main/LICENSE)
[![Paper](https://img.shields.io/badge/Paper-arxiv.2403.19522-green)](https://arxiv.org/abs/2403.19522)


</div>

This codebase is built upon [Model Soups](https://github.com/mlfoundations/model-soups) repository. 

### News and updates
- **(Aug. 2024)** Model Stock was selected as an <b>oral presentation</b> at ECCV 2024! 🎉
- We will release the full code soon. Stay tuned!

### Abstract
> This paper introduces an efficient fine-tuning method for large pre-trained models, offering strong in-distribution (ID) and out-of-distribution (OOD) performance. Breaking away from traditional practices that need a multitude of fine-tuned models for averaging, our approach employs significantly fewer models to achieve final weights yet yield superior accuracy. Drawing from key insights in the weight space of fine-tuned weights, we uncover a strong link between the performance and proximity to the center of weight space. Based on this, we introduce a method that approximates a center-close weight using only two fine-tuned models, applicable during or after training. Our innovative layer-wise weight averaging technique surpasses state-of-the-art model methods such as Model Soup, utilizing only two fine-tuned models. This strategy can be aptly coined *Model Stock*, highlighting its reliance on selecting a minimal number of models to draw a more optimized-averaged model. We demonstrate the efficacy of Model Stock with fine-tuned models based upon pre-trained CLIP architectures, achieving remarkable performance on both ID and OOD tasks on the standard benchmarks, all while barely bringing extra computational demands.

<p align="center">
<img src="images/teaser.png" style="width: 50%"; alt="Preview"/>
</p>

## Method preview
We utilize the geometric properties of the weights of fine-tuned models. We find optimal merging ratio for each layer by minimizing the distance between the merged weight and the center of the weights of fine-tuned models. The following figure shows the overview of Model Stock.
<p align="center">
<img src="images/method.png" style="width: 80%"; alt="Preview"/>
<img src="images/model_stock_eq.png" alt="Preview" style="width: 50%; height: auto;"/>
</p>

We present two scenarios: a small angle (left) and a large angle (right) between two fine-tuned weights (w_1, w_2) and a pre-trained weight (w_0). The gray triangle spans these weights, representing our search space. The optimal point on this triangle closest to the ideal center (μ) is the perpendicular foot (w_H), determined by the angle between the fine-tuned models. When the angle (θ) is large (right), w_H relies more on w_0. For details, please refer to our paper.

## Run Model Stock 
### Setup 
- Install [Model Soups](https://github.com/mlfoundations/model-soups) repository. We will use its `datasets/` and `utils.py`.
### Notebooks
- This [tutorial notebook](notebooks/model_stock_example.ipynb) will help understanding how Model Stock works. Note that it is the simplified run of Model Stock without periodic merging. 
- This [evaluation notebook](notebooks/model_stock_eval.ipynb) will show the performance of pre-uploaded Model Stock weights on ImageNet and five distribution shift benchmarks.
- End-to-end training and evaluation code will be released soon.

### Third-party implementation
- Implementation by [merge-kit](https://github.com/arcee-ai/mergekit/blob/main/mergekit/merge_methods/model_stock.py)


## How to cite

```
@inproceedings{,
    title={Model Stock: All we need is just a few fine-tuned models},
    author={Jang, Dong-Hwan and Yun, Sangdoo and Han, Dongyoon},
    year={2024},
    booktitle={Proceedings of the European Conference on Computer Vision},
}
```
