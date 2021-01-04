# Latent-Space-Boundary-Trainer-for-StyleGan2

# Project Overview
The goal of this [Google Colab](https://colab.research.google.com/) notebook is to demonstrate the steps taken to modify facial features using StyleGan2.

The basic steps include: <br />
1.) Projecting images to latent space using rolux's enconder. reference: https://github.com/rolux/stylegan2encoder <br />
2.) Hand classifying latent vectors with the desired features into two folders. In my example, seperating glasses and no glasses. <br />
3.) Training a classifier to score the probability of glasses or no glasses. <br />
4.) Feeding the latent vectors and corresponding scores into a linear SVM to find a boundary. <br />
5.) After a boundary is located, take any latent vector and move in the direction of the boundary to modify facial features. <br />
As long as you are willing to hand classify thousands of images, you cant travel in any latent direction to modify any human facial features you wish. Provided you train the StyleGan2 on something, for example cars, you can also modify a car to adopt any feature you wish as well using the same techniques demonstrated here.

## Usage

To discover how to project a real image using the original StyleGAN2 implementation, run:

1.) Project images to latent space.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/Make_latent_vectors.ipynb)

2.) Glasses Classifier.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/Glasses_classifier.ipynb)

3.) Latent Space Linear SVM.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/LatentSpaceLinearSVM.ipynb)

4.) Apply the latent directions.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/richard1634/Latent-Space-Boundary-Trainer-for-StyleGan2/blob/master/apply_latent_directions.ipynb)

<br/>
All projections, classifying, boundary training, and linear intepolation were done using `W(18,512)` dimension latent vectors rather than `W(1,512)` originaly suggestion in the StyleGan2 paper.

From [Woctezuma's read.me][wocts-readme] For more information about `W(1,*)` and `W(18,*)`, please refer to the [the original paper][stylegan2-paper] (section 5 on page 7):

> Inverting the synthesis network $g$ is an interesting problem that has many applications.
> Manipulating a given image in the latent feature space requires finding a matching latent code $w$ for it first.

The following is about `W(18,*)`:
> Previous research suggests that instead of finding a common latent code $w$, the results improve if a separate $w$ is chosen for each layer of the generator.
> The same approach was used in an early encoder implementation.

The following is about `W(1,*)`, which is the approach used in the original implementation:
> While extending the latent space in this fashion finds a closer match to a given image, it also enables projecting arbitrary images that should have no latent representation.
> Instead, we concentrate on finding latent codes in the original, unextended latent space, as these correspond to images that the generator could have produced.


# Results:
## Giving faces glasses
#### Results using my own latent directions.
![alt_text](https://user-images.githubusercontent.com/36825309/103576401-ee454280-4e87-11eb-9f3a-834c95145caa.jpg)

#### Open source directions from https://github.com/a312863063/, I see some feature entanglement with glasses and age.
![alt_text](https://user-images.githubusercontent.com/36825309/103577012-e0dc8800-4e88-11eb-81b0-f8d522ae0441.png) <br/>

## References: <br/>
This is a project I decided to start because of my interest in Generative Machine Learning. I am not assosiated with Nvidia nor the university of Hong Kong. <br/>
Image projection: https://github.com/rolux/stylegan2encoder <br/>
I learned a lot from: https://github.com/woctezuma/stylegan2-projecting-images <br/>
Boundary Trainer (University of Hong Kong): https://github.com/genforce/interfacegan <br/>
Pretrained latent directions to play around with: https://github.com/a312863063/ <br/>


<!--Definitions-->
[stylegan2-paper]: <https://arxiv.org/abs/1912.04958>
[wocts-readme]: <https://github.com/woctezuma/stylegan2-projecting-images/blob/master/README.md>
