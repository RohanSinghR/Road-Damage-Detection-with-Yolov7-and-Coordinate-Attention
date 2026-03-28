# Road Damage Detection with YOLOv7 + Coordinate Attention

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![YOLOv7](https://img.shields.io/badge/YOLOv7-00FFFF?style=flat&logo=github&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

Improved road damage detection by integrating **Coordinate Attention** into YOLOv7, achieving a **9% improvement in localization accuracy** on the RDD2022 dataset while retaining real-time inference speed.

---

## What This Does

Standard YOLOv7 treats spatial features uniformly across both axes. This project embeds **Coordinate Attention** into the deep layers of YOLOv7 to encode positional information along horizontal and vertical directions separately — improving the model's ability to detect elongated road damage patterns like cracks and ruts that span across the frame.

---

## Results

| Model | mAP@0.5 | Inference Speed |
|-------|---------|-----------------|
| YOLOv7 (baseline) | baseline | real-time |
| YOLOv7 + Coordinate Attention | **+9% localization accuracy** | real-time |

Evaluated on the **RDD2022 dataset** — a large-scale road damage dataset containing 47,420 road images from Japan, India, the United States, China, Norway, and the Czech Republic.

---

## Architecture

- **Base model:** YOLOv7
- **Modification:** Coordinate Attention integrated into deep feature extraction layers
- **Dataset:** RDD2022 (multi-country road damage dataset)
- **Task:** Multi-class road damage detection — cracks, potholes, rutting, and other surface defects

---

## Project Structure

```
├── yolov7_modified/       # YOLOv7 with Coordinate Attention integration
├── RDD2022/               # Dataset directory
├── main.ipynb             # Training, evaluation, and inference notebook
└── README.md
```

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/RohanSinghR/Road-Damage-Detection-with-Yolov7-and-Coordinate-Attention.git
cd Road-Damage-Detection-with-Yolov7-and-Coordinate-Attention
```

**2. Install dependencies**
```bash
pip install torch torchvision
pip install -r yolov7_modified/requirements.txt
```

**3. Run the notebook**

Open `main.ipynb` in Jupyter or Google Colab and follow the cells for training, evaluation, and inference.

---

## Dataset

This project uses the **RDD2022** dataset. Download it from the [official RDD2022 repository](https://github.com/sekilab/RoadDamageDetector) and place it in the `RDD2022/` directory.

---

## Key Concept: Coordinate Attention

Standard channel attention (e.g. SE blocks) aggregates spatial information into a single channel descriptor, losing positional information. Coordinate Attention decomposes global pooling into horizontal and vertical strips, preserving long-range dependency information along each axis. This is particularly effective for detecting road damage, where defects often span one spatial direction more than the other.

---

## References

- [YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors](https://arxiv.org/abs/2207.02696)
- [Coordinate Attention for Efficient Mobile Network Design](https://arxiv.org/abs/2103.02907)
- [RDD2022 Dataset](https://github.com/sekilab/RoadDamageDetector)

---

## Author

**Rohan Singh** · [LinkedIn](https://www.linkedin.com/in/rohan-singh136/) · [Portfolio](https://rohan-singh-rajendra-singh.vercel.app/)
