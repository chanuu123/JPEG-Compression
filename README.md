# JPEG Compression Pipeline (Python)

This project implements a **baseline JPEG compression algorithm** completely from scratch in Python (without relying on built-in compression libraries). It follows the classic JPEG pipeline — from color-space conversion through entropy encoding — and demonstrates how lossy image compression achieves ~10× size reduction while preserving perceptual quality.

---

## Features

- Converts input **RGB** image to **YCbCr** color space.
- Supports **4:2:0 chroma subsampling** (reduces chrominance data by 75%).
- Implements **8×8 block Discrete Cosine Transform (DCT)**.
- Applies **standard JPEG quantization matrices** for luminance and chrominance.
- Performs **Zig-Zag reordering**, **Run-Length Encoding (RLE)**, and **Huffman Coding** for entropy compression.
- Calculates **compression ratio** by comparing raw and encoded bitstreams.
- Displays intermediate results: Y, Cb, Cr channels, DCT blocks, quantized coefficients.

---

## Project Structure

* ├── mini_project_21EC39009.ipynb # Jupyter Notebook implementing the full pipeline
* ├── 21EC39009_report_jpeg.comp.pdf # Detailed project report & algorithm explanation
* └── README.md # (this file)

---
## Usage

* Place an RGB image (e.g., mandril_color.jpg) in the working directory.
* Update the image_path variable in the notebook.
* Run all cells to:
     * Convert to YCbCr
     * Subsample chroma
     * Apply DCT & Quantization
     * Encode using Zig-Zag, RLE, and Huffman coding
* Observe:
     * Visualizations of each stage
     * Compression statistics (bit count & ratio)

## Example Results

| Stage        | Key Output                                    |
| ------------ | --------------------------------------------- |
| YCbCr        | Separate Y, Cb, Cr channel images             |
| Subsampling  | 4:2:0 Cb & Cr reduced resolution              |
| DCT          | Frequency coefficients per 8×8 block          |
| Quantization | Reduced precision per JPEG tables             |
| Encoding     | Binary Huffman bitstream + \~**11.6:1** ratio |


## Background

* JPEG (Joint Photographic Experts Group) is a lossy compression standard that:

  * Separates luminance (Y) and chrominance (Cb, Cr) to exploit human vision sensitivity.
  * Uses frequency domain representation (DCT) to identify perceptually less important data.
  * Quantizes and entropy-encodes coefficients for drastic space saving.

* This project implements the above principles step-by-step, making it an excellent learning resource for image processing.

## Compression Performance

* Original data size: ~535,008 bits
* Compressed data size: ~45,943 bits
* Compression Ratio: ~11.6 : 1
  (Note: Values vary slightly with input image.)

---

## 🔧 Installation

1. Clone or download this repository.
2. Install Python 3.8+ and the following libraries:

```bash
pip install numpy opencv-python matplotlib

## Launch Jupyter Notebook:

jupyter notebook mini_project_21EC39009.ipynb

