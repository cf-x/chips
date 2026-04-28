# RW-MPJPE Weights

This file documents the joint-level weights used for **RW-MPJPE**: Risk-Weighted Mean Per Joint Position Error.

RW-MPJPE is introduced in the CHIPS paper to evaluate pressure-based in-bed 3D human pose estimation with greater emphasis on clinically important anatomical regions related to pressure ulcer risk.

---

## Important Notice

The weights in this file are provided as public evaluation metadata.

They are intended for research evaluation only and do not require separate dataset access approval.

These weights are **not** a clinical diagnosis tool, clinical guideline, medical device component, or substitute for professional medical judgment.

---

## Background

Standard **MPJPE** treats all joints equally:

```math
\mathrm{MPJPE} = \frac{1}{N}\sum_{i=1}^{N} d_i
```

where \(d_i\) is the Euclidean distance between the predicted and ground-truth 3D position of joint \(i\).

However, in in-bed clinical monitoring, different anatomical regions have different relevance to pressure ulcer risk. RW-MPJPE introduces joint-level weights to reflect this clinical relevance.

The weighting schema was defined with input from ICU nursing experts.

---

## Definition

RW-MPJPE is defined as:

```math
\mathrm{RW\text{-}MPJPE}
=
\frac{\sum_{i=1}^{N} w_i d_i}{\sum_{i=1}^{N} w_i}
```

where:

- \(d_i\): per-joint 3D position error in millimeters
- \(w_i\): clinical risk-aware weight assigned to joint \(i\)
- \(N\): number of evaluated joints

---

## Weight Table

The following table follows the 24-joint SMPL-style joint order used in our evaluation.

|   ID | Joint Name              | Weight |
| ---: | ----------------------- | -----: |
|    0 | Pelvis                  |     10 |
|    1 | Left Hip                |      5 |
|    2 | Right Hip               |      5 |
|    3 | Lumbar 1 / Lower Spine  |      1 |
|    4 | Left Knee               |      2 |
|    5 | Right Knee              |      2 |
|    6 | Lumbar 2 / Middle Spine |      1 |
|    7 | Left Ankle              |      4 |
|    8 | Right Ankle             |      4 |
|    9 | Thoracic / Upper Spine  |      1 |
|   10 | Left Forefoot / Toe     |    0.5 |
|   11 | Right Forefoot / Toe    |    0.5 |
|   12 | Neck                    |      1 |
|   13 | Left Clavicle           |    0.5 |
|   14 | Right Clavicle          |    0.5 |
|   15 | Head                    |      3 |
|   16 | Left Shoulder           |    0.5 |
|   17 | Right Shoulder          |    0.5 |
|   18 | Left Elbow              |    0.5 |
|   19 | Right Elbow             |    0.5 |
|   20 | Left Wrist              |      1 |
|   21 | Right Wrist             |      1 |
|   22 | Left Hand / Palm        |      2 |
|   23 | Right Hand / Palm       |      2 |


---

## Citation and Acknowledgement

If you use RW-MPJPE in your work, please cite the CHIPS paper once available and acknowledge the weighting metadata as follows:

```text
We used the RW-MPJPE weights provided by the CHIPS project to evaluate risk-aware joint reconstruction accuracy.
```

If you use the CHIPS dataset, please also follow the citation and acknowledgement requirements in the CHIPS Dataset Access Application and Data Use Agreement.
