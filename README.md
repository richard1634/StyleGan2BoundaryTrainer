# Latent-Space-Boundary-Trainer-for-StyleGan2

The goal of this [Google Colab](https://colab.research.google.com/) notebook is to demonstrate the steps taken to modify facial features using StyleGan2.
The basic steps include: <br />

1.) Projecting images to latent space using rolux's enconder. reference: https://github.com/rolux/stylegan2encoder <br />
2.) Hand classifying latent vectors with the desired features into two folders. In my example, seperating glasses and no glasses. <br />
3.) Training a classifier to score the probability of glasses or no glasses. <br />
4.) Feeding the latent vectors and corresponding scores into a linear SVM to find a boundary. <br />
5.) After a boundary is located, take any latent vector and move in the direction of the boundary to modify facial features. <br />


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


# Results:
## Giving faces glasses
## Results using my own latent directions
![alt_text](https://user-images.githubusercontent.com/36825309/103576401-ee454280-4e87-11eb-9f3a-834c95145caa.jpg)

### Results using my own latent directions
## Open source directions from https://github.com/a312863063/, I see some feature entanglement with glasses and age.
![alt_text](https://user-images.githubusercontent.com/36825309/103577012-e0dc8800-4e88-11eb-81b0-f8d522ae0441.png)
References: 
