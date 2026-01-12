
# Song Identification from Humming and Whistling

This project explores automatic song identification using short audio recordings of hummed or whistled melodies. The goal is to predict the correct song label based purely on melodic and acoustic information, without relying on lyrics or metadata.

The project focuses on building a clear and reproducible machine learning pipeline rather than maximising performance through complex models.

---

## Problem Overview

Identifying songs from humming or whistling is a challenging task due to variations in pitch accuracy, tempo, recording quality, and individual singing styles. Given a short audio query, the system attempts to match it to the correct song from a predefined catalogue.

This is formulated as a **multi-class classification problem**, where each class corresponds to a unique song.

---

## Approach

The project follows a standard audio machine learning workflow:

1. **Audio preprocessing**
   Audio files are loaded, normalised, and handled to account for variable-length recordings.

2. **Feature extraction**
   Acoustic features are extracted from each audio signal using the `librosa` library. These features provide a compact numerical representation of melodic and spectral characteristics.

3. **Model training**
   Classical machine learning classifiers are trained on the extracted features to predict song labels.

4. **Evaluation**
   Model performance is evaluated using classification accuracy and error analysis to better understand failure cases.

All design choices prioritise clarity, interpretability, and reproducibility.

---

## Dataset

Experiments are conducted on curated subsets of the **Hums and Whistles II** dataset, which contains audio recordings of users humming or whistling known songs.

Two publicly available subsets are provided by the dataset authors:

* **400-sample subset (≈1.09 GB)** – used for all experiments in this project
* **800-sample subset (≈2.19 GB)** – includes the 400-sample subset and can be used for larger-scale experiments

Download links:

* 400 samples: [https://github.com/thekmannn/MLEndHW_Sample/raw/main/MLEndHWII_Sample_400.zip](https://github.com/thekmannn/MLEndHW_Sample/raw/main/MLEndHWII_Sample_400.zip)
* 800 samples: [https://github.com/thekmannn/MLEndHW_Sample/raw/main/MLEndHWII_Sample_800.zip](https://github.com/thekmannn/MLEndHW_Sample/raw/main/MLEndHWII_Sample_800.zip)

In this repository, all results are reported using the **400-sample subset**. The larger subset is optional and can be used to explore how dataset size impacts model performance.

> **Note**: The dataset is not included in this repository due to its size. Please download it separately using the links above and update the data path in the notebook accordingly.

---

## Results

The experiments demonstrate that melody-based song identification is feasible, but remains challenging. Performance varies significantly depending on dataset size and feature representation.

The results highlight common failure modes, such as confusion between melodically similar songs and sensitivity to noisy or inconsistent recordings.

---


## How to Run

1. Clone this repository
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Open and run the notebook:

   ```bash
   jupyter notebook song-identification-humming.ipynb
   ```

