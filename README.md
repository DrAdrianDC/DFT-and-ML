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

The dataset (`Data.csv`) contains **336 high-throughput Density Functional Theory (DFT) calculations** of hydrogen adsorption energies ($E_{\text{ads}}$) on rocksalt-structure complex oxides. It combines physical-chemical descriptors, electronic structure properties, and local coordination environments designed to train machine learning models for accurate $E_{\text{ads}}$ predictions without requiring full surface relaxations for new configurations.

### Feature Dictionary

| Feature Name | Type | Physical Meaning / Unit | Description |
| :--- | :--- | :--- | :--- |
| `Eads` | `float64` | Adsorption Energy ($\text{eV}$) | **Target variable.** Hydrogen chemisorption energy on the rocksalt oxide surface. |
| `Bader-charge` | `float64` | Atomic Charge ($e$) | Partial charge of the active adsorption site/environment computed via Bader analysis. |
| `Ave-O2p-up` | `float64` | Band Center ($\text{eV}$) | Average energy position of the spin-up Oxygen $2p$ electronic states. |
| `Ave-O2p-down` | `float64` | Band Center ($\text{eV}$) | Average energy position of the spin-down Oxygen $2p$ electronic states. |
| `Ave-diff-EN` | `float64` | Electronegativity ($\Delta \text{EN}$) | Average Pauling electronegativity difference among local constituent atoms. |
| `Ave-diff-IE` | `float64` | Ionization Energy ($\text{eV}$) | Average ionization energy difference among local surface species. |
| `BLVE Neighbor 1–5` | `float64` | Structural / Geometric | Bond-Length / Valence-Electron environment metrics for the 1st through 5th nearest neighbors. |
| `Freq Ni` | `int64` | Coordination Count | Frequency/count of Nickel ($\text{Ni}$) cations in the immediate local surface environment. |
| `Freq Mg` | `int64` | Coordination Count | Frequency/count of Magnesium ($\text{Mg}$) cations in the immediate local surface environment. |
| `Freq Cu` | `int64` | Coordination Count | Frequency/count of Copper ($\text{Cu}$) cations in the immediate local surface environment. |
| `Freq Zn` | `int64` | Coordination Count | Frequency/count of Zinc ($\text{Zn}$) cations in the immediate local surface environment. |

### Data Integrity & Format Specifications

* **File Format:** Standard Comma-Separated Values (`Data.csv`).
* **Delimiter:** Comma (`,`).
* **Decimal Separator:** Dot (`.`) for all IEEE 754 floating-point representations.
* **Encoding:** UTF-8.
* **Missing Values:** None ($336 / 336$ complete observations).


# License
This repository is licensed under a **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License**. (See the LICENSE file).
