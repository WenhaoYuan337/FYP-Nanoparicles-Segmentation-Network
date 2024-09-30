# EMcopilot: Real-Time Electron Microscopy Image Processing and Segmentation for Nanoparticles Analysis

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
python particle_size.py
```
6. Results: The processed images and analysis results (such as segmented images, particle count, and size statistics) will be saved in the specified output folder.


## Detailed Workflow

### DM4 Processor Function

- **Input:** Folder containing `.dm4` files and the output folder where processed images and metadata will be stored.
- **Processing:** Extracts metadata from the `.dm4` files (sample name, scale, units, dimensions) and normalizes the image data.
- **Output:** Saves normalized images as `.png` in subfolders named after the sample. Metadata is logged in `samples_info.txt`.

### Segmentor Function

- **Input:** Processed images and the pre-trained segmentation model.
- **Processing:** Applies the deep learning model to segment particles, calculates particle areas, and saves the segmented images.
- **Output:** Segmentation results saved as images and particle data saved for further analysis.

### Analyzer Function

- **Input:** Segmentation results and particle area data.
- **Processing:** Analyzes the distribution of particle sizes and generates statistical information and histograms.
- **Output:** Saves a histogram visualization and logs statistics such as the average particle area and count.


## Project Outlook (extensions can be done)
- **object detection:** detection models such as Fast-RCNN or Yolo 11 can also be implemented for particle detection, which may be much faster than segmentation, and better suited for high-throughput requirements.
- **object tracking:** multi-object tracking methods (such as DeepSort), MOT, could be implemented based on the mask obtained from segmentation, to track the dynamic evolution of particles between different frames.
- **sintering:** as the characteristic of particles can defined using three key parameters, its own size, its neighboring particles distribution (may use pair distribution function), and their size. So it is hopeful to build a descriptor for this and thus differentiate two sintering mechanisms (migration/Ostwald ripening). Ref: [A machine learning-based framework for mapping hydrogen at the atomic scale](https://www.pnas.org/doi/abs/10.1073/pnas.2410968121), [Quantifying Atomically Dispersed Catalysts Using Deep Learning Assisted Microscopy](https://pubs.acs.org/doi/10.1021/acs.nanolett.3c01892), [Deep-Learning Aided Atomic-Scale Phase Segmentation toward Diagnosing Complex Oxide Cathodes for Lithium-Ion Batteries](https://pubs.acs.org/doi/10.1021/acs.nanolett.3c02441)
- **model training:** if you are interested in how segmentation models are trained and what can be done to improve network accuracy, the detailed implementation scripts could be provided.


## Questions?
Please email wy337@cornell.edu or add WeChat 13303130328 





