# Generative Adversarial Networks (GANs) for Medical Image Generation on MedMNIST

This repository contains the code, trained models, generated images, and evaluation results for our project exploring three different Generative Adversarial Network (GAN) variants applied to the MedMNIST dataset.

## Project Overview

The goal of this project was to implement and compare the performance of Least Squares GAN (LS-GAN), Wasserstein GAN (WGAN), and WGAN with Gradient Penalty (WGAN-GP) for generating medical images from the MedMNIST dataset. We trained each model for at least 50 epochs and evaluated their performance using Inception Score (IS), Fréchet Inception Distance (FID), and visual inspection. TensorBoard was used for visualization during training.

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone [repository_url]
    cd [repository_name]
    ```

2.  **Create a virtual environment (optional but recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Linux/macOS
    .\venv\Scripts\activate  # On Windows
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download the MedMNIST dataset:**
    You will need to download the specific MedMNIST dataset you intend to use (e.g., PathMNIST) and potentially modify the `data_loader.py` script to load it correctly. Refer to the [MedMNIST website](https://medmnist.com/) for download instructions and dataset details.

## Usage

1.  **Training the models:**
    Navigate to the `code/` directory and run the training scripts for each GAN variant:
    ```bash
    cd code/
    python train.py --model lsgan --epochs 50 --dataset [dataset_name]
    python train.py --model wgan --epochs 50 --dataset [dataset_name]
    python train.py --model wgangp --epochs 50 --dataset [dataset_name]
    ```
    Replace `[dataset_name]` with the specific MedMNIST dataset you are using (e.g., `pathmnist`). You can adjust the number of epochs and other hyperparameters as needed. Trained models will be saved in the `models/` directory, and generated images during training will be saved in the `generated_images/` directory.

2.  **Evaluating the models:**
    After training, run the evaluation script:
    ```bash
    python evaluate.py --model lsgan --dataset [dataset_name]
    python evaluate.py --model wgan --dataset [dataset_name]
    python evaluate.py --model wgangp --dataset [dataset_name]
    ```
    This script will calculate the Inception Score (IS) and Fréchet Inception Distance (FID) for the generated images using the trained models. The results will be saved in the `results/` directory.

3.  **Visualizing with TensorBoard:**
    To visualize the training process (losses and generated images), run TensorBoard from the root directory of the repository:
    ```bash
    tensorboard --logdir tensorboard_logs/
    ```
    Then, open your web browser and navigate to the address provided by TensorBoard (usually `http://localhost:6006`).

4.  **Visual Inspection:**
    The `results/visual_inspection_summary.md` file will contain qualitative observations based on the generated images in the `generated_images/` directory. You can manually review these images to assess their visual quality.

## Results

The `results/` directory contains:

* `is_scores.json`: JSON file containing the Inception Score for each trained GAN model.
* `fid_scores.json`: JSON file containing the Fréchet Inception Distance for each trained GAN model.
* `visual_inspection_summary.md`: Markdown file summarizing the qualitative assessment of the generated images.

The `generated_images/` directory contains subdirectories for each GAN variant, with images generated during the training process.

## Blog Post

A 5-minute reading blog summarizing the findings of this project can be found [link to your blog post here]. The blog post includes key insights, generated images, and evaluation results in an accessible format.

## LinkedIn Update

Key insights and a link to this GitHub repository have been shared on LinkedIn [link to your LinkedIn post here].

## Contributing

Contributions to this project are welcome. Please feel free to submit pull requests or open issues for any bugs or suggestions.


