# EMcopilot: Electron Microscopy Image Processing and Segmentation

**EMcopilot** is a tool designed for processing, segmenting, and analyzing electron microscopy (EM) images stored in `.dm4` format. It leverages deep learning models for image segmentation, extracts relevant metadata, and generates visualizations and statistical reports for particle analysis.

This tool is ideal for researchers working in materials science, specifically in electron microscopy image analysis, who want to process large batches of `.dm4` files, segment particle regions, and analyze particle size distributions.

## Features
- **DM4 Processing:** Extract metadata and normalize images from `.dm4` files. Metadata includes sample name, resolution, scale, and dimension.
- **Image Segmentation:** Apply a pre-trained deep learning model to segment particles in the images.
- **Particle Analysis:** Compute statistics such as the number of particles and average particle size, with results saved for further analysis.
- **Visualization:** Generate histograms and visual comparisons of original and segmented images.

## Requirements

Ensure you have the following dependencies installed:

- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Albumentations
- Torch (PyTorch)
- SciPy
- Pillow
- HyperSpy

You can install the necessary dependencies using:

```bash
pip install opencv-python-headless numpy matplotlib albumentations torch scipy pillow hyperspy
