# GAN on Fashion-MNIST

## Overview

This implementation explores Generative Adversarial Networks (GANs) using TensorFlow. The objective is to understand how generative models learn data distributions and generate new samples from random noise.

The model is trained on the Fashion-MNIST dataset, which contains grayscale images of clothing items such as shirts, trousers, dresses, shoes, and bags. Through adversarial training, the Generator learns to create realistic fashion images while the Discriminator learns to distinguish generated images from real dataset samples.

This implementation was developed as a hands-on exploration of generative modeling, adversarial learning, and custom deep learning training workflows.

---

## Dataset

### Fashion-MNIST

Fashion-MNIST is a benchmark computer vision dataset consisting of:

* 60,000 training images
* 10,000 test images
* 28×28 grayscale images
* 10 clothing categories

The dataset serves as a more challenging alternative to the traditional MNIST handwritten digits dataset and is widely used for experimenting with deep learning architectures.

---

## Architecture

### Generator

The Generator learns to transform a 100-dimensional random noise vector into a synthetic Fashion-MNIST image.

Architecture:

* Dense Layer
* Batch Normalization
* LeakyReLU Activation
* Reshape Layer
* Transposed Convolution Layers (Conv2DTranspose)
* Output Layer with Tanh Activation

The Generator's goal is to create images realistic enough to fool the Discriminator.

---

### Discriminator

The Discriminator acts as a binary classifier that determines whether an image is real or generated.

Architecture:

* Convolutional Layers
* LeakyReLU Activation
* Dropout Layers
* Flatten Layer
* Dense Output Layer with Sigmoid Activation

The Discriminator outputs a probability indicating whether an image belongs to the real dataset.

---

## Training Process

The GAN is trained using an adversarial learning framework:

1. Random noise vectors are generated.
2. The Generator converts noise into synthetic images.
3. The Discriminator evaluates both real and generated images.
4. Generator loss is calculated based on its ability to fool the Discriminator.
5. Discriminator loss is calculated based on correctly identifying real and fake samples.
6. Gradients are computed using TensorFlow's `tf.GradientTape`.
7. Both networks are updated through backpropagation.

As training progresses:

* The Generator improves image quality.
* The Discriminator becomes more difficult to fool.
* Both networks continuously adapt to each other.

---

## Concepts Explored

* Generative Adversarial Networks (GANs)
* Generator and Discriminator Architectures
* Adversarial Learning
* Deep Convolutional Networks
* Batch Normalization
* Image Synthesis from Random Noise
* Binary Cross-Entropy Loss
* Custom Training Loops
* Gradient Computation with `tf.GradientTape`
* TensorFlow Graph Optimization using `@tf.function`

---

## Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib

---

## Learning Outcomes

Through this implementation, I gained practical understanding of:

* How GANs learn data distributions without explicit labels
* The interaction between Generator and Discriminator networks
* Challenges involved in training adversarial models
* Custom model training workflows in TensorFlow
* Core concepts that form the foundation of modern Generative AI systems

---

## Sample Output

After training, the Generator is capable of producing synthetic Fashion-MNIST images by transforming random noise into recognizable fashion-related patterns learned from the dataset.

---

## Future Improvements

* Conditional GANs (cGAN)
* DCGAN Architecture Enhancements
* Higher Resolution Image Generation
* Training Stability Improvements
* Experimentation with Different Datasets
