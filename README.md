# NAO
Nonlocal Attention Operator

![Nonlocal Attention Operator (NAO) Architecture Demo.](https://github.com/fishmoon1234/NAO/blob/main/nao.png)

This repository houses the code for our spotlight paper published on NeurIPS 2024:
- [Nonlocal Attention Operator: Materializing Hidden Knowledge Towards Interpretable Physics Discovery](https://www.arxiv.org/abs/2408.07307)

**Abstract**: Despite the recent popularity of attention-based neural architectures in core AI fields like natural language processing (NLP) and computer vision (CV), their potential in modeling complex physical systems remains under-explored. Learning problems in physical systems are often characterized as discovering operators that map between function spaces based on a few instances of function pairs. This task frequently presents a severely ill-posed PDE inverse problem. In this work, we propose a novel neural operator architecture based on the attention mechanism, which we coin Nonlocal Attention Operator (NAO), and explore its capability towards developing a foundation physical model. In particular, we show that the attention mechanism is equivalent to a double integral operator that enables nonlocal interactions among spatial tokens, with a data-dependent kernel characterizing the inverse mapping from data to the hidden parameter field of the underlying operator. As such, the attention mechanism extracts global prior information from training data generated by multiple systems, and suggests the exploratory space in the form of a nonlinear kernel map. Consequently, NAO can address ill-posedness and rank deficiency in inverse PDE problems by encoding regularization and achieving generalizability. We empirically demonstrate the advantages of NAO over baseline neural models in terms of generalizability to unseen data resolutions and system states. Our work not only suggests a novel neural operator architecture for learning interpretable foundation models of physical systems, but also offers a new perspective towards understanding the attention mechanism.

## Requirements
- [PyTorch](https://pytorch.org/)


## Running experiments

**Example 1**:

To run the synthetic dataset (example 1 with sine kernels only) in the NAO paper
```
python3 Attention_synthetic_int.py 
```
Pretrained models with 2 layers and feature dimension=302 are provided, corresponding to Table 2 in the paper:
```
best_model_dk[10/20/40]_sinonly_synthetic.ckpt
```

To run the synthetic dataset with more kernels (example 1 with sine+cos+poly kernels), just uncomment lines 163-185, 212-238, then run:
```
python3 Attention_synthetic_int.py 
```
Pretrained models with 2 layers and feature dimension=302 are provided, corresponding to Table 2 in the paper:
```
best_model_dk[10/20/40]_diverse_synthetic.ckpt
```


**Example 2**:

To run the solution operator dataset (example 2) with linear (g to p) setting in the NAO paper
```
python3 Attention_darcy_gtou_int.py
```
Pretrained models with 9000 training samples, 2 layers and feature dimension=50 are provided, corresponding to Table 2 in the paper:
```
best_model_dk40_darcy_gtou.ckpt
```
A more accurate pretrained model with deeper (4) layers:
```
best_model_dk40_darcy_gtou_deeper.ckpt
```

To run the solution operator dataset (example 2) with nonlinear (b to p) setting in the NAO paper
```
python3 Attention_darcy_chitou_int.py
```

## Datasets
We provide the synthetic and solution operator datasets that are used in the paper.


## Citation

```
@inproceedings{yu2024nonlocal,
  title={Nonlocal Attention Operator: Materializing Hidden Knowledge Towards Interpretable Physics Discovery},
  author={Yu, Yue and Liu, Ning and Lu, Fei and Gao, Tian and Jafarzadeh, Siavash and Silling, Stewart},
  booktitle={Proceedings of the 38th Conference on Neural Information Processing Systems (NeurIPS 2024)}
}
```
