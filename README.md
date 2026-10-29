# Optimizations to AMPLFI: Parameter Splitting and Circular Flows

Machine learning research at the MIT LIGO Laboratory, Summer 2024, advised by Dr. Deep Chatterjee and Dr. Erik Katsavounidis.

[AMPLFI](https://arxiv.org/abs/2407.19048) uses normalizing flows to estimate the parameters of a gravitational-wave source from detector data in seconds. This project explored two ways to make it smaller and faster to train.

## What I did

- **Parameter splitting:** instead of one flow for all eight parameters, separate flows for the intrinsic parameters (chirp mass, mass ratio, distance, phase, inclination) and the extrinsic ones (sky location and polarization), comparing 5-3 and 2-6 splits with hyperparameter tuning for each.
- **Circular spline flows for sky location:** right ascension and declination are angles, so I used Neural Circular Spline Flows, which work natively on circles, instead of standard masked autoregressive flows.

## Results

- Neural Circular Spline Flows trained in about 4 hours vs. about 11 hours for the standard flow on the same sky-location task.
- Posterior calibration and searched-area comparisons are in the presentation.

## Presentation

[MIT_LIGO_2024_Presentation.pdf](MIT_LIGO_2024_Presentation.pdf)
