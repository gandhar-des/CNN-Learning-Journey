# Introduction to Convolutional Neural Networks (CNNs)

## 1. What is a CNN?

A **Convolutional Neural Network (CNN)** is a type of deep learning neural network designed especially for data with a grid-like structure, particularly images.

CNNs are widely used in computer vision tasks such as:
- Image classification
- Object detection and recognition
- Face and pose recognition
- Image segmentation
- Medical image analysis

A CNN learns useful visual patterns automatically, starting with simple features such as edges and progressing to more complex patterns such as shapes and objects.

## 2. Why not use a regular ANN for image classification?

A traditional Artificial Neural Network (ANN), especially a fully connected network, can process image data. However, it is often not the most efficient choice.

### A. Large number of parameters

An image of size 100 × 100 with 3 colour channels contains:

\[
100 \times 100 \times 3 = 30,000
\]

input values.

If these 30,000 inputs connect to 1,000 neurons, that layer alone has 30 million weights (plus biases). This increases memory and computational requirements.

### B. Overfitting risk

A model with many parameters can memorize details of its training images instead of learning patterns that generalize. This can lead to good training performance but weaker performance on unseen test images.

Overfitting is not inevitable; it depends on the model, data, and training process.

### C. Spatial structure

Images contain meaningful spatial relationships. Nearby pixels often form useful patterns such as edges and textures.

Flattening an image for a fully connected network removes its explicit 2D layout. The pixel values are still present, but the network is not naturally designed to exploit local image structure.

## 3. Why CNNs are effective

CNNs address these challenges through:

- **Local connectivity:** filters examine small regions of an image.
- **Weight sharing:** the same filter is applied across different image locations, reducing the number of parameters.
- **Feature learning:** layers learn increasingly complex visual patterns.
- **Spatial feature maps:** the network preserves spatial relationships through much of its architecture.

## 4. Basic CNN workflow

A simplified CNN often follows this pattern:

1. Input image
2. Convolution layer — extracts features
3. Activation function (commonly ReLU)
4. Pooling layer — reduces spatial dimensions
5. Additional convolution and pooling layers
6. Flattening or global pooling
7. Dense layer(s)
8. Output layer — produces the prediction

Not every CNN uses exactly this sequence. Modern architectures may use residual connections, normalization, global average pooling, and other components.

## 5. Key takeaway

CNNs are effective for image tasks because they use local filters and shared weights to learn visual patterns with fewer parameters than a comparable fully connected approach.

## Quick revision

- CNN stands for Convolutional Neural Network.
- CNNs are commonly used in computer vision.
- Fully connected networks can require many parameters for images.
- CNN filters learn local visual features.
- Weight sharing helps reduce parameter count.
- Overfitting means poor generalization to unseen data.

## Practice questions

1. What does CNN stand for?
2. Why can a fully connected network become expensive for image data?
3. What is meant by weight sharing?
4. Why is spatial structure important in images?
5. Does using an ANN always cause overfitting? Explain.
