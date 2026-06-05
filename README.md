# VesselView

> Browser-based retinal blood vessel segmentation — no installation, no account, everything runs on your device.

Upload a fundus photograph. Get a vessel map in seconds.

---

## Demo

<!-- Add screenshot or GIF here -->
*Coming soon — training pipeline in progress.*

---

## What it does

VesselView takes a retinal fundus photograph as input and outputs a binary vessel mask — a black-and-white map showing every detected blood vessel, overlaid on the original image. The entire model runs locally in your browser via ONNX Runtime Web. **Your images never leave your device.**

---

## How it works

```
Fundus image → U-Net (ONNX) → Binary vessel mask → Overlay
```

The model is a U-Net with a ResNet34 encoder, trained on the DRIVE dataset with a combined Dice + BCE loss. It is exported to ONNX and run client-side using ONNX Runtime Web with WebAssembly acceleration.

---

## Stack

| Layer | Technology |
|---|---|
| Model | U-Net + ResNet34 encoder (PyTorch) |
| Training data | [DRIVE](https://www.kaggle.com/datasets/andrewmvd/drive-digital-retinal-images-for-vessel-extraction) — 40 expert-annotated fundus images |
| Export | ONNX |
| Runtime | ONNX Runtime Web (WebAssembly) |
| Frontend | Vanilla HTML / CSS / JS |
| Hosting | GitHub Pages |

---

## Dataset

Trained on **DRIVE** (Digital Retinal Images for Vessel Extraction) — a standard benchmark for retinal vessel segmentation containing 40 fundus photographs with expert manual annotations.

- 17 training images with ground truth labels
- 16 / 4 train / val split
- Input resolution: 512 × 512
- Class imbalance: ~9% vessel pixels, ~91% background

---

## Status

🚧 **In development**

- [x] Training pipeline
- [x] Train / val split with early stopping
- [x] Dice + BCE loss
- [x] Prediction visualization
- [ ] ONNX export
- [ ] Browser runtime integration
- [ ] Frontend UI
- [ ] GitHub Pages deployment

---

## Results

<!-- Add prediction side-by-side images here -->
*Visualizations coming soon.*

---

## Local development

```bash
git clone https://github.com/your-username/vesselview
cd vesselview
# open index.html in your browser
```

No build step required — it's plain HTML, CSS, and JS.

---

## License

MIT
