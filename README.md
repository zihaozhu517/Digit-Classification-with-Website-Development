# Project: Digit Classification Using CNNs and Transformers with Website Development 

This project aims to achieve over 99% accuracy on the MNIST dataset by building and comparing two types of neural networks: a Convolutional Neural Network (CNN) and a Transformer. The goal is to optimize the architectures of these networks and assess their performance on the MNIST test set.

## Key Features:
**Network Structures:** Experimented with various CNN and Transformer architectures, tuning parameters such as layer types, filter sizes, batch sizes, and number of epochs to maximize accuracy.

**Evaluation:** The best-performing networks were trained on the full dataset and evaluated on the test set, with a focus on identifying common misclassifications and understanding their causes.

**Interactive Webpage:** Developed an Anvil-based web app that allows users to upload a 28x28 CSV file representing an MNIST digit, which the app then classifies using both the CNN and Transformer models. The app includes user authentication, image visualization, and classification feedback.

**Cloud Integration:** Leveraged AWS Lightsail for running backend Python code, enabling the Anvil app to utilize TensorFlow and other necessary libraries.

This project not only demonstrates the power of neural networks in image classification but also highlights the importance of making machine learning accessible through interactive web applications.

![self_attention](https://github.com/user-attachments/assets/b2d2bcbd-8b69-454c-8bb2-40c61d38b173)


## Model Architectures and Training
### Convolutional Neural Networks (CNNs)
- Architecture:
  - Input: 28x28 pixel images.
  - Layers: Two convolutional layers with max pooling, followed by a flatten layer, two dense layers, and an output layer with softmax activation.
  - Regularization: Dropout and L1/L2 regularization were used to prevent overfitting.
- Training Results:
  - Validation Split (20%): Achieved over 99% accuracy after 15 epochs, reaching 99.25% after 30 epochs.
  - Full Training Set: The model achieved 99.38% accuracy after 30 epochs. The accuracy started high at 98.79% and improved incrementally.
    
### Transformers
- Architecture:
  - The input images were divided into 7x7 blocks of 4x4 pixels, with each block flattened       into a 16-element vector. The transformer architecture included multi-headed self-attention and feedforward network layers, similar to BERT.
    
- Training Results:
  - Validation Split (20%): Achieved 97.38% accuracy after 100 epochs.
  - Full Training Set: Improved to 99.43% accuracy after 100 epochs, with steady performance improvements and less fluctuation compared to the 20% split.

## Key Findings and Misclassifications
Common Misclassifications: The digits 9, 4, 6, and 0 were often misclassified, likely due to similarities in their handwritten forms. For instance, the digit 9 was sometimes misclassified as 4, and 6 as 0, due to shared characteristics and certain handwriting styles.

## Accuracy Insights:

**CNNs:** The CNN model performed exceptionally well, achieving a high accuracy on both the validation split and the full training set.

**Transformers:** The transformer model, while initially less accurate, showed significant improvement when trained on the full dataset, demonstrating its potential for image classification tasks.

**Final Thoughts:** Achieving 100% accuracy is unlikely due to inherent biases in neural networks and variations in handwriting styles. However, both models achieved impressive results, with the transformer model showing considerable promise when trained on larger datasets.
