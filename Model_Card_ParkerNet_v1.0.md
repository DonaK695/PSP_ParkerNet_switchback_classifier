# Model Card: ParkerNet v1.0

## Overview

ParkerNet is a deep learning model designed to classify switchbacks in magnetic field and plasma data from the Parker Solar Probe (PSP) mission. It uses a convolutional neural network (CNN) followed by a bidirectional long short-term memory (BiLSTM) network. The model outputs a binary classification per time step: switchback or not.

This model was developed to move beyond threshold-based switchback catalogs by enabling data-driven and generalizable detection of switchbacks ( abrupt deflections in the radial component of the magnetic field often times associated with an increase in the radial velocity component of the solar wind).

---

###  Model Version

**Model Version: 1.0**  
**Notebook Version: 1.1**  

The base ParkerNet model architecture and weights are unchanged in this release. The **v1.1 update** includes new notebook documentation, cross-instrument evaluations using SPAN-I, and robustness tests.


---

## Intended Use

ParkerNet v1.0 is intended for use on time-series data from the PSP FIELDS (L2) and SWEAP-SPC (L3) instruments, with the goal of identifying candidate switchbacks. The model is not currently trained on SPAN-I (L3) data, but initial results show it performs reliably on that dataset.

---

## Training Details

- **See notebook 1 for specific training dates, different train-val splits**
- **Input Features (10):**  
  `B_r`, `B_t`, `B_n`, `Bmag`,  
  `V_r`, `V_t`, `V_n`, `V_nr`, `Vmag`, `ProtonDensity`

- **Architecture:**  
  CNN (for spatial pattern extraction) → BiLSTM (for temporal sequence modeling) → dense output layer with sigmoid activation

- **Ensemble Strategy:**  
  ParkerNet v1.0 was trained using three distinct training/validation/test splits (labeled Split M, P, and N) with different random seeds. Ensemble outputs are computed via weighted voting using AUC-PRC-based confidence scores.

---

## Performance

- **Evaluation Metric:** AUC-PRC (area under precision-recall curve)  
- **Occlusion Studies:** Conducted for each input feature to determine its relative contribution to classification performance.
- **Cross-Instrument Validation:** Run on SPAN-I datasets for Encounters E4–E8, despite not having been used during training.

---

## Robustness and Contamination

ParkerNet v1.0 was specifically evaluated for robustness to noisy or potentially contaminated features in SPC data, which tends to occur more in the tangential velocity component \( V_t \)

Two independent evaluations support the model's robustness:

- **Occlusion studies** show that removing \( V_t \) slightly improves performance, indicating the model does not rely heavily on it and likely treats it as a noisy or unhelpful signal.
- **Cross-instrument validation** reveals that performance on MAG + SPAN-I data — which lacks SPC contamination — is nearly identical to performance on MAG + SPC, demonstrating that ParkerNet is not biased toward artifacts specific to SPC measurements.

These results suggest that ParkerNet downweights or ignores unreliable features and focuses on more physically meaningful cues (e.g., \( B_r \), with modest reliance on remaining plasma variables for making predictions.

---

## Limitations

- Not trained on data from SPAN-I directly.
- Not trained on solar wind data closer to the Sun from later encounters. Especially when PSP is below the Alfven critical radius. 


---

## Recommendations

- For SPAN-I-only analysis, we recommend re-training or fine-tuning ParkerNet on SPAN-I data.
- For new encounter data, retraining may be needed to account for evolving solar wind conditions, even if SPC data is available later on.
---

##

If you use ParkerNet in your work, please cite:

> "An Iterative, Deep Learning Approach for Switchback Classification in Parker Solar Probe Data" by Dona Kuruppuaratchi, associated with manuscript number :AAS63074. 

Additionally, cite the model version used and cite the Zenodo DOI associated with the release.

---

## Model Availability

Model code, weights, and notebook examples are available at:  
**GitHub:** [https://github.com/DonaK695/PSP_ParkerNet_switchback_classifier]
---

## License

MIT License
