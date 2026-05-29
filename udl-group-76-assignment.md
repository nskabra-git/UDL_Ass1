# Problem Statement

This assignment focuses on representation learning using variants of autoencoders.

Use the following datasets:

1. CIFAR-10 dataset (available in Keras), converted to gray-level images
2. MNIST handwritten gray-scale dataset

## Dataset Preparation Requirements

Apply the following preprocessing steps to both datasets:

1. Resize all images to 28 x 28.
2. Normalize intensity levels to the range 50 to 200.
3. Split each dataset randomly into:
	- 70% training set
	- 20% validation set
	- 10% test set

## Task 1: PCA-Based Representation and Classification (3 marks)

1. Perform standard PCA using 70% of the training dataset for each dataset.
2. Identify principal components corresponding to the top 30 eigenvalues.
3. Use these PCA features to train a logistic regression classifier for 10-class image classification.
4. Evaluate on the test set and plot ROC curve(s).
5. Repeat the same pipeline using randomized PCA and compare with standard PCA.
6. Reconstruct test images using the selected principal components and compute the average signal-to-noise ratio (SNR) in dB with respect to original test images for each dataset.

## Task 2: Single-Layer Autoencoder and PCA Comparison (3 marks)

1. Train a single-layer autoencoder with the following constraints:
	- 30 hidden nodes
	- Linear activation function
	- Input normalized with appropriate mean and variance normalization
	- Decoder weight matrix is the transpose of encoder weight matrix
	- Each weight vector has unit magnitude
2. Compare eigenvectors from Task 1 with the autoencoder weight vectors.
3. Display the following as gray-scale images:
	- PCA eigenvectors from Task 1
	- Weight matrix from Task 2
4. Quantitatively analyze and comment on the relationship between PCA components and autoencoder weights.
5. Train a logistic regression classifier using autoencoded features and compare classification performance against Task 1 results for each dataset.

## Task 3: Deep Convolutional Autoencoder and SNR Analysis (4 marks)

1. Design and train an appropriate deep convolutional autoencoder with a 30-dimensional latent space.
2. Compute average SNR of reconstructed test images for each dataset.
3. Compare these SNR values with those from a single hidden-layer autoencoder configured as:
	- 30 hidden nodes
	- Sigmoid activation in the encoder
	- Linear activation in the decoder
4. Build and evaluate a 3-hidden-layer autoencoder where hidden nodes are distributed equally across the 3 layers, with:
	- Sigmoid activation in encoder layers
	- Linear activation in final decoder layer
5. Report and compare average SNR for each dataset under this architecture.

