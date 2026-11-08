---
layout: page
title: Statistically Conditioned Digital Twins
description: Predicting tipping points from measurable statistics with reservoir computing
importance: 1
category: research
---

**How much fluctuation is dangerous?** Early-warning statistics such as rising variance or autocorrelation show that a system is changing. They do not say _where_ the system will tip. This project turns statistical trend monitoring into a system-specific estimate of the transition threshold.

### Idea

Parameter-adaptable reservoir computing feeds a known control parameter into the network, so that one model learns a whole family of dynamics. In practice, that parameter is often hidden or impossible to measure.

The **statistically conditioned digital twin (SCDT)** replaces the control-parameter channel with statistics that _can_ be measured from the time series. Examples are the standard deviation $$\sigma$$, the lag-1 autocorrelation $$\rho_1$$, and the permutation entropy $$H_\text{perm}$$. These statistics act as coordinates of the dynamical regime:

$$
\mathbf{z}_{n+1} = (1-\alpha)\,\mathbf{z}_n + \alpha \tanh\!\left[ W_\text{res}\mathbf{z}_n + W_\text{in}\tilde{\mathbf{u}}_n + W_s\,\mathcal{T}_s(\mathbf{s}) \right].
$$

Only the linear readout is trained, using a handful of records from normal regimes. The twin is then run autonomously at statistical coordinates beyond the training range. Sweeping those coordinates gives survival or synchronization rates, and their 50% crossing marks the warning threshold. The network never sees the governing equations or the control parameter.

### Test systems

- **Tri-trophic food chain:** chaotic dynamics ending in predator extinction (a boundary crisis)
- **Power-system model:** transient chaos followed by voltage collapse
- **Kuramoto network:** explosive (first-order) synchronization, as an exploratory demonstration

In both collapse models, the twin reproduces the supplied fluctuation amplitude. Continued beyond the training regimes, it generates the collapse itself. Its warning thresholds fall on the conservative, lower-fluctuation side of the true transitions.

_Taehyeong Kim and Pilwon Kim, "How Much Fluctuation Is Dangerous? Predicting Tipping Points via Statistically Conditioned Digital Twins," submitted (2026). Poster presented at the KSIAM Spring Conference 2026._
