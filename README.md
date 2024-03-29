## Model Stock: All we need is just a few fine-tuned models

[Dong-Hwan Jang](https://donghwanjang.github.io)\*, [Sangdoo Yun](https://sangdooyun.github.io/)†, [Dongyoon Han](https://dongyoonhan.github.io/)†  <br> 
<sub> (\*Works done while at NAVER AI Lab, †corresponding authors) <br>

[NAVER AI LAB](https://naver-career.gitbook.io/en/teams/clova-cic/ai-lab) <br>


This repository is the official PyTorch implementation of "Model Stock: All we need is just a few fine-tuned models" | [arxiv](https://arxiv.org/abs/2403.19522)

### Abstract

> This paper introduces an efficient fine-tuning method for large pre-trained models, offering strong in-distribution (ID) and out-of-distribution (OOD) performance. Breaking away from traditional practices that need a multitude of fine-tuned models for averaging, our approach employs significantly fewer models to achieve final weights yet yield superior accuracy. Drawing from key insights in the weight space of fine-tuned weights, we uncover a strong link between the performance and proximity to the center of weight space. Based on this, we introduce a method that approximates a center-close weight using only two fine-tuned models, applicable during or after training. Our innovative layer-wise weight averaging technique surpasses state-of-the-art model methods such as Model Soup, utilizing only two fine-tuned models. This strategy can be aptly coined Model Stock, highlighting its reliance on selecting a minimal number of models to draw a more optimized-averaged model. We demonstrate the efficacy of **Model Stock** with fine-tuned models based upon pre-trained CLIP architectures, achieving remarkable performance on both ID and OOD tasks on the standard benchmarks, all while barely bringing extra computational demands.


### Updates

- Code is under internal review now 