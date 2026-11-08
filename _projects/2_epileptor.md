---
layout: page
title: Digital Twin for Seizure Transition Prediction
description: Locating seizure onset in the Epileptor model from normal activity alone
importance: 2
category: research
---

Seizure prediction is hard for two reasons. Seizures are rare and differ from one another, so models trained on seizure labels overfit easily. And the parameter that drives a seizure, such as tissue excitability, cannot be measured directly.

This team project treats seizure onset as a **critical transition** and applies the statistically conditioned digital twin (see the [SCDT project](/projects/1_scdt/)) to the Epileptor model. Here the true transition boundary is known, so it can serve as ground truth.

### Approach

- Use only the observable signal (an LFP proxy, $$x_2 - x_1$$), never the equations or the excitability parameter $$x_0$$
- Train on normal records only, conditioning on the signal's standard deviation and permutation entropy
- Sweep the statistical coordinates beyond the training range and record how often the twin's rollouts stay normal
- Define the predicted boundary as the point where the survival rate drops below 50%

### Result

For a single Epileptor node, the twin placed the seizure boundary at $$\sigma \approx 0.380$$, within about 0.3% of the ground-truth boundary. It did this without seeing a single seizure during training. The project also extends the study to a coupled three-node network, since real seizures start in one region and spread to others.

_Team Re(λ) > 0 · poster presentation, UNIST AICP 2026._
