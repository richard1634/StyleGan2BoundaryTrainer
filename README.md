# Latent-Space-Boundary-Trainer-for-StyleGan2

The goal of this [Google Colab](https://colab.research.google.com/) notebook is to demonstrate the steps taken to modify facial features using StyleGan2.
The basic steps include:
1.) Projecting images to latent space using rolux's enconder. reference: https://github.com/rolux/stylegan2encoder
2.) Hand classifying latent vectors with the desired features into two folders. In my example, seperating glasses and no glasses.
3.) Training a classifier to score the liklieness of glasses or no glasses.
4.) Feeding these into a linear SVM to find a boundary.
5.) After a boundary is located, take any latent vector and move in the direction of the boundary to modify facial features.

## Usage

To discover how to project a real image using the original StyleGAN2 implementation, run:

Latent Space Boundary Trainer
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/Make_latent_vectors.ipynb)

Glasses Classifier
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/Glasses_classifier.ipynb)

Latent Space Linear SVM
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/LatentSpaceLinearSVM.ipynb)

Apply the latent directions.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/apply_latent_directions.ipynb)
