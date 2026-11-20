---
title: Hybrid Jet Reclustering
description: Large-R jets built from groomed small-R calorimeter jets, with all primary-vertex tracks kept across the full jet area.
img: assets/img/hybrid-reclustering-scheme.png
category: Jet Definitions
importance: 3
math: true
---

## Overview

Jet reclustering is a powerful approach that enables flexibility in the use of jets with different radius parameters. 
An effective grooming from small-R jet removes pileup contamination at the calorimeter level 
but it also removes hard scatter track consitutents that happen to fall outside the surviving small-R jets. 

<div class="row">
<img src="{{ '/assets/img/hybridjets/hybrid-reclustering-ttbar.png' | relative_url }}" alt="Large-R jets vs. reclustered jets in a simulated Z' to ttbar event">
</div>
<div class="caption">Stable truth particles in a simulated $$Z' \to t\bar{t}$$ event ($$m_{Z'} = 1.5$$ TeV). Left: anti-$$k_t$$ $$R=1.0$$ jets. Right: the same jets reclustered from $$r=0.3$$ subjets: only particles inside the small-R jets survive.</div>

## The hybrid idea

Charged particles have an advantage that calorimeter clusters don't.
Pileup tracks can be rejected directly with a longitudinal impact parameter cut relative to the primary vertex (PV). 
That means tracks don't need the small-R $$p_T$$ grooming to be pileup-robust.

A **hybrid** reclustering algorithm therefore treats the two inputs differently:

- **Calorimeter:** keep the standard grooming. Small-R jets with $$p_T > 20$$ GeV are reclustered into large-R jets.
- **Tracks:** keep *all* PV-compatible tracks within the large-R jet cone, whether or not they fall inside a surviving small-R jet.

The result is a large-R jet with groomed calorimeter kinematics but a complete, pileup-suppressed set of charged constituents for substructure.

<div class="row">
<img src="{{ '/assets/img/hybridjets/hybrid-reclustering-scheme.png' | relative_url }}" alt="Scheme of a hybrid jet">
</div>
<div class="caption">A large-R jet (grey) built from $$R=0.4$$ EMTopo jets (orange). Standard reclustering keeps only the tracks associated with the small-R jets; hybrid reclustering keeps all tracks inside the large-R jet.</div>

## Motivation

Beyond boosted $$W$$/top tagging, this approach can help non-conventional searches, such as those for black hole-like and dark sector models, 
where energy is spread across many soft, wide angle objects that a hard small-R threshold would discard.

## Project goals

1. Recluster $$R=0.4$$ jets into $$R=1.0$$ jets with anti-$$k_t$$.
2. Select PV-compatible tracks and match them to jets by $$\Delta R$$.
3. Compute track-based substructure variables two ways:
   - using only tracks within $$\Delta R < 0.4$$ of the small-R jets inside the large-R jet (standard),
   - using all tracks within $$\Delta R < 1.0$$ of the large-R jet (hybrid).
4. Build ROC curves comparing standard and hybrid reclustering for $$W$$ and top tagging.

## Simulation

- $$\sqrt{s} = 14$$ TeV $$pp$$ collisions with full ATLAS detector simulation and pileup overlay reweighted to HL-LHC conditions.
- *MC Samples:* Pythia 8 multijet samples 
- *If time permits:* we will use a sample of $$W$$ jets from $$W' \to WZ \to qqqq$$ with $$m_{W'} = 2$$ TeV, reweighted to a flat $$p_T$$ spectrum.

## First results

First look at this method showed promising results.

<div class="row">
<img src="{{ '/assets/img/hybridjets/hybrid-event-display.png' | relative_url }}" alt="Event display of reclustered jets">
<img src="{{ '/assets/img/hybridjets/hybrid-nsmallR.png' | relative_url }}" alt="Number of R=0.4 jets per R=1 jet">
</div>
<div class="caption">Left: event display with $$R=0.4$$ jets (red) reclustered into $$R=1.0$$ jets (blue). Right: number of $$R=0.4$$ jets per $$R=1.0$$ hybrid jet.</div>

<div class="row">
<img src="{{ '/assets/img/hybridjets/hybrid-mass.png' | relative_url }}" alt="Track-based large-R jet mass">
<img src="{{ '/assets/img/hybridjets/hybrid-ntrk.png' | relative_url }}" alt="Large-R track multiplicity">
</div>
<div class="caption">Track-based large-R jet mass (left) and track multiplicity (right), using tracks associated with the $$R=0.4$$ jets vs. all tracks in the $$R=1.0$$ jet.</div>

## Next steps

- Signal vs. background substructure comparisons ($$W$$ and top jets vs. multijets).
- ROC curves for standard vs. hybrid reclustering

## Links

- Talk on event-level jet definitions for non-conventional searches: [Indico](https://indico.cern.ch/event/1214001/contributions/5159187/attachments/2556618/4410220/291122evJetDef.pdf)
- ATLAS PUB Note draft: *Hybrid jet reclustering: a new approach to build jets* (internal, in preparation)