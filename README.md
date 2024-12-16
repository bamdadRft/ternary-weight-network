# ternary-weight-network
This project implements a method to approximate the weights of a classic Convolutional Neural Network (CNN) model into ternary weights , while maintaining high classification accuracy. Ternarizing weights reduces memory and computational costs, making it highly suitable for deployment on resource-constrained devices
# key-features
Ternary Transformation Function: A modified version of the standard hyperbolic tangent function is applied to the model weights. This function outputs values in the set  based on predefined thresholds:

If the tanh output is greater than 0.666, the value is set to 1.

If the tanh output is less than -0.666, the value is set to -1.

If the tanh output is within the range , the value is set to 0.

Weight Normalization: Each weight is scaled by dividing it by its mean absolute value , ensuring proper scaling before applying the ternary transformation. A small epsilon value  is added to avoid division by zero. The transformation formula is:

Here,  represents the original weight,  is the mean absolute value, and  is the ternary-transformed weight.

KL Divergence Regularization: Ensures the ternarized weights closely approximate the original weights by minimizing the Kullback-Leibler divergence between their probability distributions.

Seamless Integration: Train and evaluate the model with either the original or ternarized weights.

Minimal Accuracy Loss: Despite ternarization, the model demonstrates a low accuracy drop.

# results
Baseline Accuracy (Original Weights): 72.96%

Accuracy with Ternarized Weights: 70.65%

The small drop in accuracy () highlights the effectiveness of the ternarization approach in preserving model performance.

# how-it-works
Ternary Weight Transformation

The weights of the CNN model are transformed into ternary values  using the described hyperbolic tangent function. This step reduces the size and complexity of the model, making it more efficient for deployment without significant performance loss.

Training with KL Divergence Regularization

During training, the original weights are compared with their ternarized counterparts using KL divergence. This regularization ensures the ternarized weights are a close approximation of the original weights while preserving model accuracy.

Evaluation with Ternarized Weights

To evaluate the model with ternarized weights, the original weights are temporarily replaced with their ternarized equivalents. After evaluation, the original weights are restored.

Accuracy Evaluation

The model is evaluated on its ability to classify correctly using both original and ternarized weights. Despite the reduced precision, the ternarized model achieves nearly the same accuracy as the original.

