# Overview

This project is about Density Functional Theory (DFT) and Machine Learning applied to Physical Chemistry, and it is part of my Postdoc research at Vanderbilt University.
The title of the publication is:  
#### "DFT and machine learning for predicting hydrogen adsorption energies on rocksalt complex oxides."

![Graphical-Abstract-Fig](https://github.com/DrAdrianDC/DFT-and-ML/assets/157868503/6a7224a3-3ad0-434d-9aad-82353655cd47)

Published on Theoretical Chemistry Accounts, part of the collection Machine Learning meets Quantum Chemistry
Now available: https://link.springer.com/article/10.1007/s00214-024-03124-x

The prediction of hydrogen adsorption energies on complex oxides by integrating DFT calculations and Machine Learning is considered. 
In particular, 14 descriptors for electronic and geometric properties evaluation are adapted within a 336 hydrogen adsorption energy 
dataset created. Supervised learning techniques were explored to establish an accurate predictive model. With the Deep Neural Network 
results, a MAE of about 0.06 eV is achieved. This research highlights the synergistic potential of DFT and Machine Learning for accelerating 
the exploration of materials for catalysis, with a significance to assisting in the understanding of structure-reactivity relationship of high-entropy oxides.


# Project

    Description: Predicting hydrogen adsorption energies on rocksalt complex oxides combining DFT calculations and machine learning.
    Tools & Techniques: Python, pandas, scikit-learn, tensorflow, keras, Linear Regression, 
    Random Forest, Neural networks, Deep Learning, data visualization
    Links: GitHub Repository

# Requirements

* Python 3.8.3
* TensorFlow 2.10.0
* Pandas 1.0.5
* Numpy 1.23.4
* Scikit-learn 1.3.2
* Keras 2.10.0




The full dataset was obtained from DFT calculations. (See Data.xlsx)

## Dataset 

## Dataset Overview

The dataset (`Data.csv`) comprises **336 density functional theory (DFT) calculated surface configurations** of hydrogen adsorption energies ($E_{\text{ads}}$) on rocksalt-structure complex oxides. 

To model $E_{\text{ads}}$ without computationally heavy DFT structural relaxations, each sample is represented by a set of **14 physical-chemical, electronic, and structural descriptors** defined in detail in the [Supporting Information](Supporting-Information.pdf).

---

### Feature Dictionary & Descriptor Definitions

| Feature Name | Type | Unit / Range | Definition & Source (SI) |
| :--- | :--- | :--- | :--- |
| `Eads` | `float64` | $\text{eV}$ | **Target Variable.** Hydrogen adsorption energy on the rocksalt oxide surface site ($E_{\text{ads}} = E_{\text{surf+H}} - E_{\text{surf}} - \frac{1}{2}E_{\text{H}_2}$). |
| `Bader-charge` | `float64` | $e$ | Partial atomic charge of the active surface adsorption site, computed via Bader charge analysis. |
| `Ave-O2p-up` | `float64` | $\text{eV}$ | Average position (band center) of the spin-up Oxygen $2p$ electronic states relative to the Fermi level. |
| `Ave-O2p-down` | `float64` | $\text{eV}$ | Average position (band center) of the spin-down Oxygen $2p$ electronic states relative to the Fermi level. |
| `Ave-diff-EN` | `float64` | Dimensionless | Average Pauling electronegativity difference ($\Delta\text{EN}$) between the central active oxygen site and its nearest-neighbor cations. |
| `Ave-diff-IE` | `float64` | $\text{eV}$ | Average first ionization energy difference ($\Delta\text{IE}$) between constituent metal cations in the active local environment. |
| `BLVE Neighbor 1–5` | `float64` | Arbitrary Units | **Bond-Length Valence-Electron (BLVE)** metrics for nearest neighbors 1 through 5, capturing local geometric distortions and local electron density overlap. |
| `Freq Ni` | `int64` | Count [$0, 5$] | Local coordination frequency/count of Nickel ($\text{Ni}$) cations surrounding the active surface oxygen site. |
| `Freq Mg` | `int64` | Count [$0, 5$] | Local coordination frequency/count of Magnesium ($\text{Mg}$) cations surrounding the active surface oxygen site. |
| `Freq Cu` | `int64` | Count [$0, 5$] | Local coordination frequency/count of Copper ($\text{Cu}$) cations surrounding the active surface oxygen site. |
| `Freq Zn` | `int64` | Count [$0, 5$] | Local coordination frequency/count of Zinc ($\text{Zn}$) cations surrounding the active surface oxygen site. |

---

### Summary Statistics

* **Total Samples:** 336
* **Missing / Null Values:** 0
* **Input Features:** 14 (6 electronic/chemical + 5 BLVE structural + 4 local composition counts)
* **Target Feature:** 1 (`Eads`)
* **Format:** Comma-separated values (`Data.csv`), dot (`.`) decimal separator, UTF-8 encoding.
# License
This repository is licensed under a **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License**. (See the LICENSE file).
