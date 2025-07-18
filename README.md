# 🧵 Image Quilting for Texture Synthesis and Transfer  
**CS445: Computational Photography — Project 2**  
📅 **Due Date:** Feb 26, 2025  
👨‍💻 **Author:** Taha Wasiq  
📓 **Notebook:** `Image_Quilting_Project2.ipynb`

---

## 🧠 Overview

This project implements the **Image Quilting** algorithm from the SIGGRAPH 2001 paper by Efros and Freeman. The goal is to generate new textures and perform texture transfer by intelligently stitching together small image patches.

Applications include:
- Texture synthesis
- Texture transfer
- Image inpainting
- Image blending and completion

---

## 🚀 Implemented Functions

### ✅ `quilt_random(sample, out_size, patch_size)`
Randomly samples patches from a source image to synthesize a larger texture with no overlap or seam matching. Simple but yields visible discontinuities.

### ✅ `quilt_simple(sample, out_size, patch_size, overlap, tol)`
Places overlapping patches and uses **sum of squared differences (SSD)** to find and randomly sample patches that best match previous overlap regions. Allows some randomness controlled by `tol`.

### ✅ `quilt_cut(sample, ...)`
Adds **seam finding** using the provided `cut` function to blend overlapping regions and reduce visual seams.

### ✅ `texture_transfer(sample, target, ...)`
Implements texture transfer by combining texture matching with patch similarity to a target guide image. Produces visual effects like "face-on-toast" transfer.

---

## 🖼 Sample Results

Generated images demonstrate:
- The difference between random and overlap-based quilting
- Seam smoothing with min-cost cuts
- Texture transferred from bricks, cloth, or grass onto face and shape templates

Results are saved in the `results/` folder.

---

## 📂 File Structure

```text
/
├── Image_Quilting_Project2.ipynb       # ✔️ Main notebook
├── utils.py                            # ✔️ Contains seam finding helper (`cut`)
├── samples/                            # ✔️ Input texture and target images
├── results/                            # ✔️ Generated outputs
├── report.pdf                          # ✔️ Final write-up report
└── README.md                           # ✔️ This file
