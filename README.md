# Spatio-Temporal Graph Convolutional Networks
[![issues](https://img.shields.io/github/issues/hazdzz/STGCN)](https://github.com/hazdzz/STGCN/issues)
[![forks](https://img.shields.io/github/forks/hazdzz/STGCN)](https://github.com/hazdzz/STGCN/network/members)
[![stars](https://img.shields.io/github/stars/hazdzz/STGCN)](https://github.com/hazdzz/STGCN/stargazers)
[![License](https://img.shields.io/github/license/hazdzz/STGCN)](./LICENSE)

## About
The PyTorch version of STGCN implemented by the paper *Spatio-Temporal Graph Convolutional Networks:
A Deep Learning Framework for Traffic Forecasting* with tons of bugs fixed.

## Paper
https://arxiv.org/abs/1709.04875

## Related works
1. TCN: [*An Empirical Evaluation of Generic Convolutional and Recurrent Networks for Sequence Modeling*](https://arxiv.org/abs/1803.01271)
2. GLU and GTU: [*Language Modeling with Gated Convolutional Networks*](https://arxiv.org/abs/1612.08083)
3. ChebyNet: [*Convolutional Neural Networks on Graphs with Fast Localized Spectral Filtering*](https://arxiv.org/abs/1606.09375)
4. GCN: [*Semi-Supervised Classification with Graph Convolutional Networks*](https://arxiv.org/abs/1609.02907)

## Related code
1. TCN: https://github.com/locuslab/TCN
2. ChebyNet: https://github.com/mdeff/cnn_graph
3. GCN: https://github.com/tkipf/pygcn

## Model structure
<img src="./figure/stgcn_model_structure.png" style="zoom:100%" />

## Differents of code between mine and author's
1. Fix tons of bugs 
2. Add Early Stopping approach
3. Add Dropout approach
4. Offer a different set of hyperparameters
5. Offer config files for two different categories graph convolution

## Requirements
To install requirements:
```console
pip3 install -r requirements.txt
```

## The result for road traffic prediction on dataset METR-LA (15/30/60 mins) (train: val: test = 70: 15: 15)
### 15 mins (H=3)
| Model (paper) | Model (code) | Laplacian matrix type | Gated activation function | MAE | RMSE | WMAPE |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| STGCN (Cheb) | STGCN_ChebConv (Ks=3, Kt=3) | sym | GLU | 3.896181 | 8.180521 | 7.669819% |
| STGCN (1<sup>st</sup>) | STGCN_GCNConv (Kt=3) | sym | GLU | 3.703660 | 7.685864 | 7.290832% |

### 30 mins (H=6)
| Model (paper) | Model (code) | Laplacian matrix type | Gated activation function | MAE | RMSE | WMAPE |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| STGCN (Cheb) | STGCN_ChebConv (Ks=3, Kt=3) | sym | GLU | 5.415257 | 10.542593 | 10.661624% |
| STGCN (1<sup>st</sup>) | STGCN_GCNConv (Kt=3) | sym | GLU | 4.518740 | 8.863177 | 8.896550% |

### 60 mins (H=12)
| Model (paper) | Model (code) | Laplacian matrix type | Gated activation function | MAE | RMSE | WMAPE |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| STGCN (Cheb) | STGCN_ChebConv (Ks=3, Kt=3) | sym | GLU | 6.710720 | 12.415373 | 13.215713% |
| STGCN (1<sup>st</sup>) | STGCN_GCNConv (Kt=3) | sym | GLU | 5.997484 | 11.498759 | 11.811108% |

## The result for road traffic prediction on dataset PEMS-BAY (15/30/60 mins) (train: val: test = 70: 15: 15)
### 15 mins (H=3)
| Model (paper) | Model (code) | Laplacian matrix type | Gated activation function | MAE | RMSE | WMAPE |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| STGCN (Cheb) | STGCN_ChebConv (Ks=3, Kt=3) | sym | GLU | 1.515749 | 3.039355 | 2.439110% |
| STGCN (1<sup>st</sup>) | STGCN_GCNConv (Kt=3) | sym | GLU | 1.472308 | 2.987471 | 2.369206% |

### 30 mins (H=6)
| Model (paper) | Model (code) | Laplacian matrix type | Gated activation function | MAE | RMSE | WMAPE |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| STGCN (Cheb) | STGCN_ChebConv (Ks=3, Kt=3) | sym | GLU | 1.940019 | 4.057035 | 3.121926% |
| STGCN (1<sup>st</sup>) | STGCN_GCNConv (Kt=3) | sym | GLU | 1.910708 | 3.948517 | 3.074757% |

### 60 mins (H=12)
| Model (paper) | Model (code) | Laplacian matrix type | Gated activation function | MAE | RMSE | WMAPE |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| STGCN (Cheb) | STGCN_ChebConv (Ks=3, Kt=3) | sym | GLU | 2.316922 | 4.714354 | 3.728668% |
| STGCN (1<sup>st</sup>) | STGCN_GCNConv (Kt=3) | sym | GLU | 2.306092 | 4.701984 | 3.711238% |
