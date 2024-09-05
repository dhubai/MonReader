# FlipDetect: Page Flip Detection

## Project Overview

FlipDetect enhances document digitization with a mobile solution specifically designed to aid the visually impaired, researchers, and anyone requiring efficient, bulk document scanning. This innovative tool simplifies the process by automating the detection of page flips from video frames, capturing high-resolution images for processing.

## Innovation and Technology

Using advanced artificial intelligence and computer vision technologies, FlipDetect detects when a page is flipped using just low-resolution camera previews. The system then processes these images to:
- Recognize and crop document corners accurately.
- Dewarp images for a flat document appearance.
- Enhance text contrast against backgrounds for clearer visibility.
- Preserve text formatting using machine learning.

## Model Architecture

The FlipDetect solution employs a Convolutional Neural Network (CNN) with the following architecture:
- **Input Layer**: Accepts images resized to 128x128 pixels.
- **Convolutional Layers**: Three layers with filters of sizes 32, 64, and 128, respectively, each followed by a MaxPooling layer to reduce spatial dimensions.
- **Flatten Layer**: Converts the 2D matrix output from the convolutional layers into a 1D vector.
- **Dense Layers**: Two fully connected layers with ReLU activation functions, culminating in an output layer with a softmax activation function to predict two classes: "flip" or "notflip".

## Data Preparation

- **Image Loading and Normalization**: Images are loaded from specified directories, resized to 128x128 pixels, and normalized to a range of [0, 1].
- **Label Encoding**: Images are labeled as "flip" or "notflip" based on their directories and converted into a categorical format suitable for the classification task.
- **Data Splitting**: The dataset is divided into training, validation, and testing sets to ensure robust model evaluation.

## Training Details

- **Optimizer**: The model uses the Adam optimizer for efficient gradient descent optimization.
- **Loss Function**: Categorical cross-entropy loss is employed to handle the multi-class classification problem.
- **Training Parameters**: The model is trained over 10 epochs with a batch size of 16, ensuring a balance between computational efficiency and model accuracy.
- **Evaluation**: The model's performance is monitored through accuracy and loss metrics on both training and validation sets.

## Evaluation and Performance Metrics

- **F1 Score**: The model achieved an F1 score of 0.9715, indicating high accuracy in detecting page flips, which demonstrates its effectiveness for the intended application.

## Model Saving

The trained model is saved using the HDF5 format (`.h5`). A recommendation is made to use the native Keras format for future model saves to leverage the latest features.

## Achievements

Our solution integrates seamlessly into existing data workflows, providing a tool that is not only cutting-edge but also highly accessible. The model's performance was rigorously evaluated, achieving an F1 score of 0.9715, indicating high accuracy in detecting page flips.

## Conclusion

FlipDetect represents a significant step forward in document digitization technology, offering a practical solution that meets the needs of a diverse user base. Its development is a testament to the potential of artificial intelligence to revolutionize everyday tasks and workflows.
