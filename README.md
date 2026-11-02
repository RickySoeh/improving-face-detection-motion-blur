# Improving Face Detection Under Motion Blur Using Deep Learning-Based Face Image Restoration

This repository contains the source code accompanying the paper:

**Improving Face Detection Under Motion Blur Using Deep Learning-Based Face Image Restoration**

## Repository Structure

- `Dataset_Filtering_Code/`
  - MTCNN-based filtering of the Helen dataset, resizing to 256×256, and generation of the four blur levels
- `Models/`
  - U-Net
  - ViT
  - ViT-U-Net
- `Evaluation/`
  - `Thesis_Face_Detection_Rate_Evaluation.ipynb`: face detection rate on blurred and restored images (RetinaFace, YuNet)
  - `Detection_Localization_Evaluation.ipynb`: localization-based evaluation (IoU ≥ 0.5), precision, recall, false positives, 95% Wilson confidence intervals and exact McNemar tests
  - Result files: `summary.csv`, `per_image_results.csv`, `mcnemar.csv`, `iou_sweep.csv`, `gt_boxes.csv`, `paper_tables.md`

## Dataset

Due to GitHub file size limitations, the dataset is provided separately.

Please refer to **Dataset_Link.txt** for the download link.

## How to Run

All notebooks were run on Google Colab with an NVIDIA Tesla T4 GPU.

1. Run `Dataset_Filtering_Code/Pre_Thesis_Dataset_Filtering.ipynb` to build the processed dataset.
2. Train the restoration models in `Models/` (each notebook saves its deblurred test outputs).
3. Run the notebooks in `Evaluation/` to reproduce the detection and localization results.

## Evaluation Metrics

- Restoration quality: PSNR, SSIM
- Face detection: detection rate (at least one face with confidence > 0.9)
- Localization: correct localization (IoU ≥ 0.5 with the reference face box), precision, recall, false positives
- Statistics: 95% Wilson confidence intervals, exact McNemar tests with Holm correction

## Face Detectors

- RetinaFace
- YuNet
