# MOFformer

![fig1](https://user-images.githubusercontent.com/64190846/167797065-1a104b35-a949-4775-93d4-c7310d90afbb.jpg)

- `MOfformer` is a multi-modal pretraining Transformer that is designed to enable universal transfer learning (UTL) in Metal-Organic Frameworks (MOFs).
- `MOFformer` was trained with 1 M hypothetical MOFs (hMOFs) generated by [pormake](https://github.com/Sangwon91/PORMAKE) in the pretraining step. 
- The goal of pretrainig is to learn `local features` and `global features` in MOFs
  - local features : Metal node, Organic linker, Functional groups, etc.
  - global features : Topology, Pore volume, Surface area, etc.

- The pretraining tasks are as belows:

1) MTP (MOF Topology Prediction)
2) MOC (Metal node/Organic linker Classification)
3) VFP (accessible Void Fraction Prediction)

## Architectures
![fig2](https://user-images.githubusercontent.com/64190846/167792454-32ea32ad-29ba-4230-a15d-7e51c3ce8412.jpg)

- `MOFformer` takes two different representations as input
1) Atom-based Graph Representation : CGCNN w/o pooling layer -> local features
2) 3D Structural Image Representation : 1D flatten patches of 3D energy grid -> global features


## [Install](https://github.com/hspark92/MOFformer/blob/master/INSTALL.md)
## [prepare data](https://github.com/hspark92/MOFformer/blob/master/DATA.md)
## [Training](https://github.com/hspark92/MOFformer/blob/master/TRAIN.md)

## Finetuning Results
### 1. Finetuning to predict GCMC, MD, DFT properties when the number of data is from 1k to 20k
![0_best_mae](https://user-images.githubusercontent.com/64190846/167793802-2e18a15a-24f5-4cc9-88e2-9254f4fb20d0.jpg)
reference
1. `energy histogram` [Prediction of O2/N2 Selectivity in Metal−Organic Frameworks via High-Throughput Computational Screening and Machine Learning](https://pubs.rsc.org/en/content/articlelanding/2019/me/c8me00050f)
2. `Descriptor-based ML model` [Prediction of O2/N2 Selectivity in Metal−Organic Frameworks via High-Throughput Computational Screening and Machine Learning](https://pubs.acs.org/doi/abs/10.1021/acsami.1c18521)
3. `Crystal Graph Convolutional Neural Networks` [Crystal Graph Convolutional Neural Networks for an Accurate and Interpretable Prediction of Material Properties](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.120.145301)
### 2. UTL (in progress)
![그림1](https://user-images.githubusercontent.com/64190846/167795007-add29f6a-d77b-4f0d-bbc9-ff1b3411faeb.png) 
reference
1. [Prediction of O2/N2 Selectivity in Metal−Organic Frameworks via High-Throughput Computational Screening and Machine Learning](https://pubs.acs.org/doi/abs/10.1021/acsami.1c18521)
2. [Using Machine Learning and Data Mining to Leverage Community Knowledge for the Engineering of Stable Metal–Organic Frameworks](https://pubs.acs.org/doi/10.1021/jacs.1c07217)
