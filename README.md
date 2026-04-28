# Robust In-Bed Human Pose and Shape Estimation from Pressure Images with Clinical Awareness

This repository accompanies the paper:

**Robust In-Bed Human Pose and Shape Estimation from Pressure Images with Clinical Awareness**

We introduce **CHIPS**, a clinically grounded dataset for pressure-based in-bed human pose and shape estimation, and **BA-PIHMR**, a robust reconstruction framework designed for clinically realistic bed configurations.

---

## Important Notice

- Dataset access is controlled and subject to approval, approved de-identified subsets may be provided upon request.
- The release scope of the dataset will follow ethical approval, privacy protection requirements, and institutional data governance policies.

To request access, please complete and sign the following form:

**[CHIPS Dataset Access Application and Data Use Agreement](CHIPS_Dataset_Access_Application.pdf)**

Submit the completed PDF to:

**Chenfang Fang**  
Email: [fang_chenfang@mail.ustc.edu.cn](mailto:fang_chenfang@mail.ustc.edu.cn)

Suggested email subject:

```text
CHIPS Dataset Application - [PI Full Name] - [Institution]
```

---

## Introduction

Estimating the 3D pose and shape of in-bed patients is important for clinical applications such as pressure ulcer prevention, sleep quality monitoring, and patient behavior analysis.

Pressure sensing provides a privacy-preserving and unobtrusive alternative to RGB cameras and wearable sensors. However, existing pressure-based datasets are often collected in simplified environments and do not fully reflect realistic clinical settings.

CHIPS addresses this limitation by collecting pressure data in an ICU-simulated environment with clinically relevant bed configurations, including head-of-bed elevation, multiple pillows, bedsheets, and medical-grade airbed effects.

---

## Dataset Overview

CHIPS is designed for pressure-based 3D human pose and shape estimation in clinically realistic in-bed scenarios.

The dataset contains:

- **207,508 synchronized frames**
- **16 subjects**
- **50 clinically relevant ICU-style scenarios**
- De-identified pressure images
- Derived 3D pose and SMPL-based shape annotations, where applicable
- Clinical risk-aware evaluation metadata for RW-MPJPE

The data collection setup used synchronized pressure sensing and multi-view RGB capture for annotation generation. The standard requestable/releasable dataset includes de-identified pressure images and derived annotations. Raw multi-view RGB recordings are **not included in the standard release** unless separately approved.

---

## Method Overview

We propose **BA-PIHMR**, a Blur-Aware Pressure-Image-supported Human Mesh Reconstruction framework.

The model includes:

- A pressure image encoder for spatial feature extraction
- **Bed-State FiLM** for adapting to different bed configurations
- **Blur-Aware Attention** for handling pressure blur and ambiguous contact regions
- A temporal Transformer for sequence modeling
- An SMPL regressor for 3D human pose and shape recovery

---

## RW-MPJPE Weights

We introduce **RW-MPJPE**: Risk-Weighted Mean Per Joint Position Error.

RW-MPJPE assigns higher evaluation importance to joints and anatomical regions that are more clinically relevant to pressure ulcer risk.

- The weighting schema was defined with input from ICU nursing experts.
- The weights are provided as public evaluation metadata.
- Full details are available in [RW-MPJPE-weights.md](RW-MPJPE-weights.md).

---

## Dataset Access and Use Policy

Use of the CHIPS dataset is restricted to approved **non-commercial academic research** purposes only.

Researchers must not:

- Attempt to re-identify, de-anonymize, or contact any individual represented in the dataset.
- Redistribute, sublicense, sell, lease, or transfer the dataset to any third party.
- Use the dataset for commercial products, commercial services, or revenue-generating activities.
- Use the dataset for clinical diagnosis, clinical decision-making, patient monitoring, patient care, or any regulated medical use.
- Store the dataset on publicly accessible servers or unapproved cloud services.
- Use the dataset to train generative AI systems, large language models, or other machine learning systems for commercial deployment without a separate written agreement.

All dataset access requests must be reviewed and approved by the data provider. Approved users must follow the terms in the **CHIPS Dataset Access Application and Data Use Agreement**.

---

## License

The repository code and documentation are released under the [MIT License](LICENSE), unless otherwise stated.

The CHIPS dataset is **not** released under the MIT License. Dataset access and use are governed separately by the CHIPS Dataset Access Application and Data Use Agreement.

---

## Ethical Approval

This study was performed in line with the principles of the Declaration of Helsinki.

Ethical approval was granted by the **Medical Research Ethics Committee of The First Affiliated Hospital of the University of Science and Technology of China (USTC)**.

Approval No.: **2023KY-211**

---

## Acknowledgements

We thank the nurses from the Department of Intensive Care Unit, The First Affiliated Hospital of USTC, for their clinical expertise and support in defining the RW-MPJPE weight system and clinically relevant data collection scenarios.

This work is supported by the Research Funds of the Centre for Leading Medicine and Advanced Technologies of IHM.

---

## Citation

The formal citation will be added after publication.

If you use the CHIPS dataset, BA-PIHMR code, or RW-MPJPE weights, please cite the paper once available and acknowledge the dataset as follows:

```text
This research used the CHIPS dataset (Robust In-Bed Human Pose and Shape Estimation from Pressure Images with Clinical Awareness), provided by Chenfang Fang, University of Science and Technology of China (USTC).
```

---

## Contact

For dataset access, questions, or reporting potential privacy/security concerns, please contact:

**Chenfang Fang**  
Email: [fang_chenfang@mail.ustc.edu.cn](mailto:fang_chenfang@mail.ustc.edu.cn)
