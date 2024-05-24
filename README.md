#!/bin/bash

# Exit immediately if a command exits with a non-zero status.
set -e

# Variables
REPO_URL="https://github.com/your-username/Image-Classifier-ViT.git"
PYTHON_VERSION="3.11"
VENV_DIR="venv"

# Display commands and their arguments as they are executed.
set -x

# Introduction
echo "This project is based on the Vision Transformer (ViT) model for image classification."

# Features
echo "Features:"
echo "- Image classification using Vision Transformer (ViT)"
echo "- Easy setup and deployment"
echo "- Modular code for ease of understanding and extension"

# Prerequisites
echo "Prerequisites:"
echo "- Python 3.11 (ensure Python 3.11.x is installed on your machine)"
echo "- Git"

# Fork the Repository
echo "Fork the Repository:"
echo "1. Go to the project repository on GitHub."
echo "2. Click the 'Fork' button in the top-right corner to create your own copy of the repository."

# Clone the Repository
echo "Cloning the repository..."
git clone ${REPO_URL}
cd Image-Classifier-ViT

# Install Python 3.11 if not installed
if ! command -v python3.11 &> /dev/null
then
    echo "Python 3.11 could not be found, installing..."
    sudo apt update
    sudo apt install -y python3.11 python3.11-venv
fi

# Create a Virtual Environment
echo "Creating virtual environment using Python 3.11..."
python3.11 -m venv ${VENV_DIR}

# Activate the Virtual Environment
echo "Activating virtual environment..."
source ${VENV_DIR}/bin/activate

# Install Dependencies
echo "Installing dependencies..."
python -m ensurepip --upgrade
pip install -r requirements.txt

# Usage Instructions
echo "To run the image classification script, use the following command:"
echo "python classify.py --image_path path_to_your_image"

# Contributing
echo "Contributing:"
echo "1. Fork the repository."
echo "2. Create a new branch: git checkout -b feature/your-feature-name"
echo "3. Make your changes and commit them: git commit -m 'Add some feature'"
echo "4. Push to the branch: git push origin feature/your-feature-name"
echo "5. Open a pull request."

# License
echo "This project is licensed under the MIT License. See the LICENSE file for details."

# Deactivate debugging
set +x

echo "Setup complete. The virtual environment is activated."
echo "To reactivate the environment, run: source ${VENV_DIR}/bin/activate"
