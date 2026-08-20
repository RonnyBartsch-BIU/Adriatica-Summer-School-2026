[README.md](https://github.com/user-attachments/files/31253336/README.md)
# Physiological Coupling in Practice
### From Cardiorespiratory Synchrony to Heart–Brain Interactions

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RonnyBartsch-BIU/Adriatica-Summer-School-2026/blob/main/Adriatica2026_Tutorial_Bartsch.ipynb)

Hands-on tutorial, **Adriatica Summer School 2026** (University of Chieti, 31 Aug – 4 Sep 2026)
Ronny Bartsch, Department of Physics, Bar-Ilan University

**Click the badge above to run the tutorial in Google Colab — no installation, no downloads.**

---

## What the tutorial covers

This hands-on tutorial introduces the analysis of coupling between physiological systems using real
polysomnographic recordings. Working in a Jupyter notebook (Google Colab, no installation
required), participants extract heart rate and brain wave amplitude from raw ECG and EEG
signals, visualize cardiorespiratory coupling via synchrogram analysis, and use Granger
causality to detect directed interactions between heart and brain across sleep stages. The
session covers the full workflow: signal extraction, stationarity assessment, and
interpretation of coupling strength and directionality. The results connect directly to the
concepts introduced in the accompanying lecture.

Three sensors, one set of methods:

| Block | Sensor | What we extract |
|---|---|---|
| 1–2 | Smartphone on the chest (Phyphox) | heartbeat, breathing, RSA, first synchrogram |
| 3 | Wrist accelerometer (SOMNOwatch, as used in the German National Cohort) | pulse waves from wrist motion alone |
| 4–5 | Sleep-lab polysomnography (SIESTA) | synchronization across sleep stages, directed heart–brain coupling |

Everything runs on numpy / scipy / matplotlib / pandas — all pre-installed in Colab.

## Record your own data

Blocks 1–2 work on any recording you make yourself:
**Phyphox** → *Acceleration with g* → phone flat on the sternum, screen up → lie still for
5 minutes → export CSV → replace the filename in the first cell of Block 1.

## Data files

| File | Content |
|---|---|
| `spontaneous-breathing.csv` | Phyphox chest accelerometry, ~6 min, spontaneous breathing |
| `paced-breathing.csv` | as above, breathing paced by metronome at 3 breaths/min |
| `somnowatch_sleep.csv` | 10-min sleep excerpt, 3-axis wrist acceleration @ 128 Hz |
| `somnowatch_rpeaks.txt` | simultaneously recorded ECG R-peak times (s) |
| `somnowatch_flow.csv` | simultaneously recorded respiratory flow @ 4 Hz (take-home exercise D) |
| `siesta_deep.csv`, `siesta_rem.csv` | respiration @ 4 Hz, 5-min single-stage segments |
| `siesta_deep_rpeaks.txt`, `siesta_rem_rpeaks.txt` | R-peak times for the same segments (s) |
| `siesta_granger_light.csv`, `siesta_granger_deep.csv` | heart rate + EEG α amplitude @ 1 Hz, 10-min segments |

All segments are de-identified and provided for educational use only.

## References

- Günther M., Kantelhardt J.W., Bartsch R.P. (2022). The reconstruction of causal networks in
  physiology. *Frontiers in Network Physiology* **2**:893743.
  [doi:10.3389/fnetp.2022.893743](https://doi.org/10.3389/fnetp.2022.893743)
- Zschocke J. et al. (2022). Reconstruction of pulse wave and respiration from wrist
  accelerometer during sleep. *IEEE Trans. Biomed. Eng.* **69**:830.
  [doi:10.1109/TBME.2021.3107978](https://doi.org/10.1109/TBME.2021.3107978)
- Bartsch R.P., Liu K.K.L., Bashan A., Ivanov P.Ch. (2015). Network physiology: how organ
  systems dynamically interact. *PLoS ONE* **10**:e0142143.
- Klösch G. et al. (2001). The SIESTA project polygraphic and clinical database.
  *IEEE Eng. Med. Biol. Mag.* **20**:51.

Full conditional Granger pipeline:
[github.com/moritz-g/causal_networks_physiology](https://github.com/moritz-g/causal_networks_physiology)
Time Delay Stability toolbox: [pypi.org/project/TDSpy](https://pypi.org/project/TDSpy/)
