# 🧠 Exploring the Relationship between Brain Hemisphere States and Frequency Bands through Deep Learning

<p align="center">
  <img src="https://img.shields.io/badge/Published-IEEE%20Access-00629B?style=for-the-badge&logo=ieee&logoColor=white" />
  <img src="https://img.shields.io/badge/arXiv-2509.14078-b31b1b?style=for-the-badge&logo=arxiv&logoColor=white" />
  <img src="https://img.shields.io/badge/Dataset-Zenodo-1682D4?style=for-the-badge&logo=zenodo&logoColor=white" />
  <img src="https://img.shields.io/badge/Frameworks-TensorFlow%20%7C%20PyTorch-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" />
</p>

<p align="center">
  <a href="https://doi.org/10.1109/ACCESS.2026.3722615"><b>📄 Read the paper (IEEE Access, DOI: 10.1109/ACCESS.2026.3722615)</b></a>
</p>

---

## 📌 Overview

This repository contains the code, models, and results for a study on classifying **EEG brain-hemisphere states** (left vs. right) across different **frequency bands** (delta, theta, alpha, beta, gamma) using multiple **deep learning optimization techniques**.

Three neural network architectures — a **deep dense network**, a **shallow three-layer network**, and a **convolutional neural network (CNN)** — were implemented in both **TensorFlow** and **PyTorch**, and evaluated across optimizers including **Adam, SGD, RMSprop, Adagrad, Adadelta, and FTRL**.

> **Key finding:** Adagrad and RMSprop consistently outperform other optimizers across frequency bands — Adagrad excels in the **beta** band, while RMSprop achieves superior performance in the **gamma** band. Classical ML methods (Linear SVM, Random Forest) reach perfect classification with far faster training, but deep neural networks show a clear edge in real-time **neurofeedback** simulation.

---

## 🗂️ Repository Structure

```
├── MODEL/                  # Model architectures (dense / shallow / CNN)
├── Torch/                  # PyTorch implementations
├── Participant 1–10/       # Per-participant EEG data & results
├── Result/                 # Aggregated experiment results
├── Regenerate-New-Result/  # Scripts to reproduce/regenerate results
├── ROC_plot/                # ROC-AUC plots per band/optimizer
├── SHAP_plot/               # SHAP explainability plots
├── kaggle5user/              # 5-user dataset subset & notebooks
├── code_error/               # Debug / error-analysis notebooks
├── *.ipynb                   # Optimizer-specific experiment notebooks (Adam, SGD, RMSprop, FTRL, ...)
├── *_output.csv               # Raw experiment outputs per optimizer
├── Channels.dat               # EEG channel configuration
└── CITATION.cff                # Citation metadata
```

---

## 🧪 Methodology at a Glance

| Stage | Description |
|---|---|
| **1. Data** | EEG recordings from 10 participants under visual stimuli, band-filtered into delta/theta/alpha/beta/gamma |
| **2. Preprocessing** | Frequency-band filtering, hemisphere-state labeling (binary: left vs. right) |
| **3. Modeling** | Deep dense network, shallow 3-layer network, CNN — built in TensorFlow & PyTorch |
| **4. Optimization** | Adam, SGD, RMSprop, Adagrad, Adadelta, FTRL compared across all bands |
| **5. Evaluation** | Accuracy, Precision, Recall, F1, ROC-AUC + SHAP-based explainability |
| **6. Application** | Real-time neurofeedback simulation to test practical regulation performance |

---

## 📊 Highlights

- ⚡ **Adagrad** → best in the **beta** band
- ⚡ **RMSprop** → best in the **gamma** band
- 🌀 **Adadelta** → most robust across cross-model evaluation
- 🐢 **SGD & FTRL** → inconsistent performance
- 🧩 **Classical ML (SVM, Random Forest)** → perfect classification, 50–100× faster training
- 🎯 **Deep neural network** → 44.7% regulation rate in real-time neurofeedback vs. 0% for classical methods

---

## 📚 Publications & Related Work

This project has resulted in the following outputs — from preprint to peer-reviewed journal publication:

| Type | Title | Link |
|---|---|---|
| 🏛️ **Journal Article (IEEE Access)** | *Exploring the Relationship between Brain Hemisphere States and Frequency Bands through Deep Learning* | [doi.org/10.1109/ACCESS.2026.3722615](https://doi.org/10.1109/ACCESS.2026.3722615) |
| 📝 **Preprint (arXiv)** | *...through Classical Machine Learning and Deep Learning Optimization Techniques with Neurofeedback* | [arXiv:2509.14078](https://arxiv.org/abs/2509.14078) |
| 💾 **Dataset & Software (Zenodo)** | EEG Visual Stimuli dataset & code release | [doi.org/10.5281/zenodo.17176638](https://doi.org/10.5281/zenodo.17176638) |
| 📈 **Kaggle Dataset** | 10-user EEG dataset used in this study | [kaggle.com/datasets/connect2robiul/10userdatasets](https://www.kaggle.com/datasets/connect2robiul/10userdatasets/) |
| 🔁 **Additional Material** | Additional results, revisions, and supplementary material generated during the peer-review process | [round3-result-and-other](https://github.com/connect2robiul/round3-result-and-other/tree/main) |

---

## 📖 Citation

If you use this work, please cite the journal publication and/or the dataset:

```bibtex
@article{islam2026exploring,
  title   = {Exploring the Relationship between Brain Hemisphere States and Frequency Bands through Deep Learning},
  author  = {Islam, Robiul and Ignatov, Dmitry I. and Kaberg, Karl and Nabatchikov, Roman},
  journal = {IEEE Access},
  year    = {2026},
  doi     = {10.1109/ACCESS.2026.3722615}
}

@misc{islam2025exploring,
  title   = {Exploring the Relationship between Brain Hemisphere States and Frequency Bands through Deep Learning Optimization Techniques},
  author  = {Islam, Robiul and Ignatov, Dmitry I. and Kaberg, Karl and Nabatchikov, Roman},
  year    = {2025},
  eprint  = {2509.14078},
  archivePrefix = {arXiv},
  url     = {https://arxiv.org/abs/2509.14078}
}

@software{islam2025eeg,
  author    = {Islam, Robiul},
  title     = {Exploring the Relationship between Brain Hemisphere States and Frequency Bands through Deep Learning: EEG Visual Stimuli},
  month     = sep,
  year      = 2025,
  publisher = {Zenodo},
  version   = {EEGVisualStimuli},
  doi       = {10.5281/zenodo.17176638},
  url       = {https://doi.org/10.5281/zenodo.17176638}
}
```

---

## 👤 Author

**Robiul Islam** —  Innopolis University, Russia
🔗 [Personal site](https://connect2robiul.github.io/newversion/) · [GitHub](https://github.com/connect2robiul)
A huge thanks to **Dmitry Ignatov** ([hse.ru/en/staff/dima](https://www.hse.ru/en/staff/dima/)) for his invaluable help and for covering the APC for IEEE Access — this publication would not have been possible without him.
---

## 📄 License

Please refer to the repository license (or contact the author) for terms of reuse of code and data.
