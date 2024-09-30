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
```

## How to Use
1. Initialize the environment: Ensure that you have the necessary dependencies installed, as listed in the Requirements section.

2. Place your DM4 files in a folder: The script will prompt you to provide the folder where your .dm4 files are located.

3. Set the output folder: You'll be prompted to specify an output folder for saving the results. The folder will be created if it does not exist.

4. Choose the segmentation model: You will need to provide a pre-trained deep learning model (.pt or .pth file) for the segmentation task. Place the model in the working directory, and the script will allow you to select it.

5. Run the script: The script will process the .dm4 files, segment the images, and generate the required analysis.

```bash
python emcopilot.py
```
6. Results: The processed images and analysis results (such as segmented images, particle count, and size statistics) will be saved in the specified output folder.


## Detailed Workflow
- **DM4 Processor Function**
Input: Folder containing .dm4 files and the output folder where processed images and metadata will be stored.
Processing: Extracts metadata from the .dm4 files (sample name, scale, units, dimensions) and normalizes the image data.
Output: Saves normalized images as .png in subfolders named after the sample. Metadata is logged in samples_info.txt.
- **Segmentor Function**
Input: Processed images and the pre-trained segmentation model.
Processing: Applies the deep learning model to segment particles, calculates particle areas, and saves the segmented images.
Output: Segmentation results saved as images and particle data saved for further analysis.
- **Analyzer Function**
Input: Segmentation results and particle area data.
Processing: Analyzes the distribution of particle sizes and generates statistical information and histograms.
Output: Saves a histogram visualization and logs statistics such as the average particle area and count.

## Example Use Case



