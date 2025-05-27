# Isolated Arabic Sign Language Recognition Using a Transformer-based Model and Landmark Keypoints
This repository is for the following paper ["Isolated Arabic Sign Language Recognition Using a Transformer-based Model and Landmark Keypoints"](https://dl.acm.org/doi/abs/10.1145/3584984?casa_token=d4qt9dIqcKYAAAAA%3A5wdtHrTP5vCXVvVwGWBs0HCAlcSKPN1b9_kj5w--j7Dw_35gB2hacwGBfsP_txLJD8HpycmAugg)

## Introduction 
Pose-based approaches for sign language recognition provide light-weight and fast models that can be adopted in real-time applications. This article presents a framework for isolated Arabic sign language recognition using hand and face keypoints. We employed MediaPipe pose estimator for extracting the keypoints of sign gestures in the video stream. Using the extracted keypoints, three models were proposed for sign language recognition: Long-Term Short Memory, Temporal Convolution Networks, and Transformer-based models. Moreover, we investigated the importance of non-manual features for sign language recognition systems and the obtained results showed that combining hand and face keypoints boosted the recognition accuracy by around 4% compared with only hand keypoints. The proposed models were evaluated on Arabic and Argentinian sign languages. Using the KArSL-100 dataset, the proposed pose-based Transformer achieved the highest accuracy of 99.74% and 68.2% in signer-dependent and -independent modes, respectively. Additionally, the Transformer was evaluated on the LSA64 dataset and obtained an accuracy of 98.25% and 91.09% in signer-dependent and -independent modes, respectively. Consequently, the pose-based Transformer outperformed the state-of-the-art techniques on both datasets using keypoints from the signer’s hands and face.

## Environment and Dependencies
This project is implemented in a Jupyter Notebook using TensorFlow-Keras. It requires the following Python libraries:

* tensorflow (recommended version: 2.11.0 or compatible with your setup)

- keras (matching your TensorFlow version)

- mediapipe

- opencv-python

- numpy

- scikit-learn

Please ensure you have Jupyter Notebook installed and running in a compatible Python environment (Python ≥ 3.7).

## Datasets
Two isolated SLR datasets were utilized in this study, the KArSL dataset for Arabic SLR and
the LSA64 dataset for Argentinian SLR. We used a subset of the KArSL dataset containing 100
word-level dynamic signs in the form of RGB videos. The signs are performed by three signers and
repeated 50 times by each signer. The LSA64 dataset contains 64 signs in Argentinian sign language.

- KArSL can be downloaded [Here](https://hamzah-luqman.github.io/KArSL/)

- LSA64 can be dowloaded [Here](https://facundoq.github.io/datasets/lsa64/)
  
## Methods

The study investiagted several methods for encoding the key[point sequence. 
- LSTM
- TCN
- Transformer-based encoder

![Framework](https://github.com/snalyami/Pose_SLR/blob/main/framework%20(1).png)
## Results

Accuracy on the KArSL-100 dataset.

| **Model**       | **Hand** | **Face** | **Signer1** | **Signer2** | **Signer3** |  **Avg.** | **All signers** |
| --------------- | :------: | :------: | :---------: | :---------: | :---------: | :-------: | :-------------: |
| **LSTM**        |     ✓    |     ✗    |    62.9%    |    41.5%    |    60.1%    |   54.8%   |      84.0%      |
|                 |     ✓    |     ✓    |    54.8%    |    35.7%    |    61.9%    |   50.8%   |      82.1%      |
| **TCN**         |     ✓    |     ✗    |    67.2%    |    46.6%    |    65.7%    |   59.8%   |      88.9%      |
|                 |     ✓    |     ✓    |    68.6%    |    38.8%    |    59.5%    |   55.6%   |      85.0%      |
|                 |     ✓    |     ✓    |    69.6%    |    54.1%    |    69.4%    |   64.4%   |      95.1%      |
| **Transformer** |     ✓    |     ✓    |  **75.3%**  |  **59.4%**  |  **70.0%**  | **68.2%** |    **99.7%**    |

Accuracy on the LSA64 dataset.

| **Method**               | **Signer-dependent** | **Signer-independent** |
| ------------------------ | :------------------: | :--------------------: |
| **Proposed Transformer** |      **98.25%**      |       **91.09%**       |

## Running the Code

Please follow the instructions in the [Jupyter Notebook](https://github.com/snalyami/Pose_SLR/blob/main/Pose_based_SLR.ipynb)

## Citations

For those who find the provided code beneficial for their research or work, we kindly request citing the following papers:

```
@article{10.1145/3584984,
author = {Alyami, Sarah and Luqman, Hamzah and Hammoudeh, Mohammad},
title = {Isolated Arabic Sign Language Recognition Using a Transformer-based Model and Landmark Keypoints},
year = {2024},
issue_date = {January 2024},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
volume = {23},
number = {1},
issn = {2375-4699},
url = {https://doi.org/10.1145/3584984},
doi = {10.1145/3584984},
abstract = {Pose-based approaches for sign language recognition provide light-weight and fast models that can be adopted in real-time applications. This article presents a framework for isolated Arabic sign language recognition using hand and face keypoints. We employed MediaPipe pose estimator for extracting the keypoints of sign gestures in the video stream. Using the extracted keypoints, three models were proposed for sign language recognition: Long-Term Short Memory, Temporal Convolution Networks, and Transformer-based models. Moreover, we investigated the importance of non-manual features for sign language recognition systems and the obtained results showed that combining hand and face keypoints boosted the recognition accuracy by around 4\% compared with only hand keypoints. The proposed models were evaluated on Arabic and Argentinian sign languages. Using the KArSL-100 dataset, the proposed pose-based Transformer achieved the highest accuracy of 99.74\% and 68.2\% in signer-dependent and -independent modes, respectively. Additionally, the Transformer was evaluated on the LSA64 dataset and obtained an accuracy of 98.25\% and 91.09\% in signer-dependent and -independent modes, respectively. Consequently, the pose-based Transformer outperformed the state-of-the-art techniques on both datasets using keypoints from the signer’s hands and face.},
journal = {ACM Trans. Asian Low-Resour. Lang. Inf. Process.},
month = jan,
articleno = {3},
numpages = {19},
keywords = {Sign language recognition, arabic sign language, gesture recognition, pose recognition, TCN, transformer}
}
```

```
@article{sidig2021karsl, 
           title={KArSL: Arabic Sign Language Database}, 
           author={Sidig, Ala Addin I and Luqman, Hamzah and Mahmoud, Sabri and Mohandes, Mohamed},
            journal={ACM Transactions on Asian and Low-Resource Language Information Processing (TALLIP)}, 
           volume={20}, 
           number={1}, 
           pages={1--19}, 
           year={2021}, 
           publisher={ACM New York, NY, USA} 
           }
```

