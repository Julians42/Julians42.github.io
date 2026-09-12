---
title: 'Google X Internship and some thoughts on AIWP'
date: 2026-10-02
permalink: /posts/2026/09/googlepreprint/
tags:
  - google
  - software
  - ai/ml
---


<p align="center">
  <img src='/images/all_j_photos/us_hurricanes.png' width="850" />
</p>

_**Observed and forecasted extreme precipitation for the five landfalling tropical cyclones in the U.S. in 2024 and in 2025 before September 30th, 2025.** Rows display event-integrated accumulation (spanning 24 hours before to 72 hours after landfall) for hurricanes Beryl (**A**–**D**), Debby (**E**–**H**), Francine (**I**–**L**), Helene (**M**–**P**), and Milton (**Q**–**T**). Forecasts were initialized at least 72 hours before the landfall time listed in IBTrACS at 06:00 or 18:00 UTC. Columns show observed IMERG accumulated precipitation (**A**, **E**, **I**, **M**, **Q**) alongside model probability of exceedance (PoE) over 50-member ensembles at the 100 mm threshold for IFS (**B**, **F**, **J**, **N**, **R**), operational AIFS-CRPS (**C**, **G**, **K**, **O**, **S**), and Laxmi (**D**, **H**, **L**, **P**, **T**). Solid contours overlaid on forecast panels indicate the observed region where IMERG accumulated precipitation exceeded 100 mm. Annotated values in the upper left of each forecast panel report the event-level Brier score evaluated at the 100 mm accumulation threshold defined across the active region, which is indicated by the dashed box. Image from our arXiv [paper](https://arxiv.org/abs/2609.03210)._

*Note: The views expressed here are my own and do not necessarily reflect those of Google or Google DeepMind. The work described is publicly available in our [arXiv preprint](https://arxiv.org/abs/2609.03210).*


## Recent Progress in AIWP

Progress in AI for weather forecasting has been meteoric. Over the last 4 years, a myriad of models has been released, many of which improved medium-range forecast accuracy and have demonstrated the range of ML architectures that can be applied to the problem. Of the something like two dozen models released in that time, 3 main developments stand out to me. 

**2022-2023:** First, simply beating physics-based models on many smooth variables at medium-range and beyond (e.g., [ECMWF's AI WeatherQuest](https://aiweatherquest.ecmwf.int/)). I find it striking that small teams can produce models that are competitive with established centers. Operationally, however, the value medium range forecasts provide is not forecasting the mean temperature well but in the extremes: heat waves, heavy precipitation, derechos, etc. AI weather prediction models (AIWP) still lag on these tail [metrics](https://www.science.org/doi/10.1126/sciadv.aec1433) because, particularly for deterministic models, they tend to exchange uncertainty for [smoothness](https://www.science.org/doi/10.1126/science.adi2336).


**2023-2025:** Second, the switch from mean squared error-based loss functions to probabilistic loss functions has both addressed the smoothness problem and allowed for probabilistic forecasts. Using ML to build probabilistic models is actually much easier than it is for physical models, which must separately build and calibrate physically consistent perturbations on top of the analysis for initialization. For AIWP, that process is a consequence of the loss function, which balances accuracy and ensemble spread, and is further tuned out to longer horizons by the rollout fine-tuning.

**2026:** The third, and most recent advance is augmenting existing AIWP model architectures, which are primarily trained to ERA5 reanalysis, with observational data. While the holy grail of weather forecasting is direct observations-to-observations forecasting, the leading end-to-end systems, e.g., [Aardvark](https://www.nature.com/articles/s41586-025-08897-0), aren't yet outperforming physics-based models on smooth global metrics. Likely with more observations these models may eventually overtake current AIWP, but that is not the case now.

At Google X, my 6-month residency project focused on this third category. We built on AIWP's success forecasting atmospheric dynamics training to ERA5 by augmenting one of the output variables, precipitation, with satellite data. The work is available on [arXiv](https://arxiv.org/abs/2609.03210). A similar approach has also been used in Google Deepmind's operational weather forecasting model, WeatherNext3, for multiple surface variables. Deepmind has also released a [cyclone model](https://www.nature.com/articles/s41586-026-10953-2), which I find particularly interesting because it jointly optimizes the dynamical variables and hurricane track data from IBTrACS to directly forecast cyclone locations and intensities. The headline result is a 24-hour lead-time improvement in track accuracy over ECMWF's ENS and NOAA's HAFS-A model. 

## What's next?
I think there's still quite a bit of accuracy to be gained by augmenting ERA5-trained models with observations. Beyond bias-correcting surface variables, incorporating prognostic variables could sharpen the model's learned representation of the atmospheric state. Soil moisture from SMAP, for instance could improve late-afternoon convective-storm forecasting. Satellite images of tropical Pacific clouds could do the same for subseasonal predictability of the Madden-Julian Oscillation.

Core model development is also worth watching. ERA6 is being released at 13km resolution next year, about double ERA5's 25km, and I'd expect each of the frontier labs will race to publish a higher-resolution version of their model. 

Model initialization is ripe for development too. Physical models use data assimilation to get an initial state that is accurate and dynamically consistent with the model. Accuracy comes from the volume and quality of observations, while dynamical consistency comes from 4D-VAR and prevents the model from exciting unphysical waves that inflate forecast errors. Operational AIWP uses these same initial conditions, which are published every 6 hours. That reliance limits how often forecasts can be produced, and it limits which observations enter the analysis; if ECMWF (or another center providing initial conditions) chooses not to use an observation, it won't be constraining the initial state. WeatherNext3 demonstrates that geostationary data can be used to increase the frequency of model initialization to hourly. A more challenging next step would be to do the same with data from A-train satellites. That's why I think companies like [WindBorne](https://windbornesystems.com/), which are collecting there own proprietary data from a network of weather balloons, might be particularly well positioned for medium-range forecasting with their own data assimilation pipeline, provided they have access to enough compute to train frontier architectures.
