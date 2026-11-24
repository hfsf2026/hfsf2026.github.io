---
title: Topo-cluster calibration with a transformer network
description: Calibrating topological cell signal clusters in the ATLAS calorimeter with a transformer network
img:
contact: Peter Loch (topo-cluster calibration), Jad Sardain (technical support)
category: Constituent Calibration
importance: 1
math: true
---

## Overview

The application of machine-learning-based local calibrations for clusters of topologically connected cell signals (topo-clusters) in the ATLAS calorimeters has been shown to perform significantly better than the standard <u>l</u>ocal (hadronic) <u>c</u>ell <u>w</u>eighting (LCW) calibration that first employs a classification with respect to the cluster signal source, followed by a hadronic calibration and out-of-cluster and dead material corrections. The LCW calibration shows limitations in its performance due to its implementation that is based on multi-dimensional binned lookup tables filled with average probability or scale factors derived from single particle MC simulations. These tables can introduce steep bin-to-bin transitions and, due to the independent averaging, the loss of correlations between the inputs.

Most of the performance improvements in terms of accuracy (signal linearity) and precision (signal resolution) achieved with the ML-based calibrations arise from the use of more inputs (features), including measures for the pile-up activity in the collision event, and the smooth multi-dimensional calibration function learned for each cluster from those. The calibration models used so far implement deep neural networks (DNN) either with a leaky Gaussian loss function \[[ATL-PHYS-PUB-2023-019](https://cds.cern.ch/record/2866591/files/ATL-PHYS-PUB-2023-019.pdf)\] or, better performing and with the additional benefit of predicting an uncertainty for the learned calibration function, with a probabilistic loss function implementing a Gaussian mixture PDF in a Bayesian neural network (BNN) \[[SciPost Phys. 19, 155(2025)](https://scipost.org/SciPostPhys.19.6.155)\] with weight functions connecting nodes. This latter approach requires complex inference software. A more straight forward inference is possible with the recently studied DNN with scalar weights employing a <u>H</u>eteroscedastic <u>G</u>aussian <u>M</u>ixture (HGM) loss function that also learns the calibration and the associated uncertainties (a paper is in preparation, for now see [summary by Isabel Sainz (Heidelberg)](https://indico.cern.ch/event/1686481/contributions/7094802/attachments/3275541/5852243/MLCluster_meeting_15.05.26.pdf)).   

Of of the observed issues with the DNN used in the HGM topo-cluster calibration is the lack of extrapolation for clusters that have features sets that have not been part of the training sample. Here transformer networks seem to be a promising alternative which can provide meaningful calibration functions even for topo-clusters with feature sets outside of the space covered in the network training. We suggest to look into implementing such a network as a replacement of the DNN but possibly using the same or a similar HGM loss function.  
