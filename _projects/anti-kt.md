---
title: Anti-kt Clustering
description: Sequential recombination with infrared and collinear safety.
img: assets/img/anti-kt.svg
category: Jet Definitions
importance: 1
math: true
---

Every project page is just a Markdown file in the `_projects/` folder. Write normal Markdown here: headings, lists, links, code, and math.

## Overview

The anti-$$k_t$$ algorithm defines the distance between particles $$i$$ and $$j$$ as

$$
d_{ij} = \min\left(k_{t,i}^{-2},\, k_{t,j}^{-2}\right)\frac{\Delta R_{ij}^2}{R^2}, \qquad d_{iB} = k_{t,i}^{-2}.
$$

Hard particles cluster soft particles around them first, giving round, regular jets.

## Figures

Put images in `assets/img/` and use a row to lay them side by side:

<div class="row">
  <img src="{{ '/assets/img/anti-kt.svg' | relative_url }}" alt="">
  <img src="{{ '/assets/img/kt.svg' | relative_url }}" alt="">
  <img src="{{ '/assets/img/cone.svg' | relative_url }}" alt="">
</div>
<div class="caption">A row of three images. Add <code>class="wide"</code> to one to make it take two thirds.</div>

<div class="row">
  <img class="wide" src="{{ '/assets/img/cone.svg' | relative_url }}" alt="">
  <img src="{{ '/assets/img/anti-kt.svg' | relative_url }}" alt="">
</div>
<div class="caption">A two-thirds / one-third row.</div>

## Links

- Paper: [arXiv:0802.1189](https://arxiv.org/abs/0802.1189)
- Code: [FastJet](https://fastjet.fr)
