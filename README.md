# VesselView

Browser-based retinal blood vessel segmentation — upload a fundus image, get a vessel map in seconds. No installation, no account, everything runs on your device via ONNX Runtime Web.

## What it does

Takes a retinal fundus photograph as input and outputs a binary vessel mask — a black-and-white map showing every blood vessel detected, overlaid on the original image.

## Status

🚧 In development — training pipeline in progress.

## Dataset

Trained on [DRIVE](https://www.kaggle.com/datasets/andrewmvd/drive-digital-retinal-images-for-vessel-extraction) (Digital Retinal Images for Vessel Extraction) — 40 fundus images with expert annotations.

## Stack

- Model: U-Net (PyTorch)
- Deployment: ONNX Runtime Web
- Frontend: Vanilla HTML/CSS/JS
- Hosting: GitHub Pages

