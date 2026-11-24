---
title: Topo-cluster calibration with a transformer network
description: Calibrating topological cell signal clusters in the ATLAS calorimeter with a transformer network
img:
category: Constituent Calibration
importance: 1
math: true
---

## Overview

The application of machine-learning-based local calibrations for clusters of topologically connected cell signals (topo-clusters) in the ATLAS calorimeters has been shown to perform signifcantly better than the standard <u>l</u>ocal (hadronic) <u>c</u>ell <u>w</u>eighting (LCW) calibration that first employs a classification with respect to the cluster signal source, followed by a hadronic calibration and out-of-cluster and dead material corrections. The LCW calibration shows limitations in its performance due to its implementation that is based on multi-dimensional binned lookup tables filled with average probability or scale factors derived from single particle MC simulations. These tables can introduce steep bin-to-bin transitions and the loss of correlations between the inputs.

Most of the performance improvements in terms of accuracy (signal linearity) and precision (signal resolution) achieved with the ML-based calibrations arise from the use of more inputs (features), including measures for the pile-up activity in the collision event, 
and the smooth multi-dimensional calibration function learned from those.
