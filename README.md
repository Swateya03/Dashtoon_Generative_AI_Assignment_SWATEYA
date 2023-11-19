# Color-Aware Multi-Style Transfer

Color-Aware Multi-Style Transfer is an innovative approach to image style transfer, designed to enhance the visual aesthetics of generated images by preserving the style-color correlation. This method allows users to manipulate the appearance of a source image, while maintaining the texture and colors associated with a target style image. Unlike traditional Gram matrix-based optimization, our approach considers the relationship between colors and styles, particularly beneficial when dealing with target style images that exhibit multiple style types.

## Model
VGG-19: A pre-trained convolutional neural network (CNN) from PyTorch's model zoo. It is used for feature extraction during style transfer.

## Key Features

- **Color-Aware Optimization:** Our method introduces a simple yet effective modification to classic Gram matrix-based optimization, focusing on the correlation between colors and styles.
- **Multi-Style Transfer:** Accommodate images with diverse styles effortlessly, making it a versatile solution for a range of artistic preferences.
- **User Interaction:** Users can manually select color associations, offering enhanced control over the style transfer process for personalized artistic outcomes.
  
### Note : We have manually selected color associations using    SELECT_MATCHES = True  

## Validation and User Study

We validated our Color-Aware Multi-Style Transfer through qualitative comparisons and conducted study with our original dataset. The results showcase the simplicity, ease of implementation, and visually appealing outcomes, especially when dealing with images that feature multiple styles.

## Samples of manual selection done in the assignment

![Screenshot (670)](https://github.com/Swateya03/Dashtoon_Generative_AI_Assignment_SWATEYA/assets/142562275/4e5c70ec-1726-41b7-9fb6-2328424a6da7)

![Screenshot (671)](https://github.com/Swateya03/Dashtoon_Generative_AI_Assignment_SWATEYA/assets/142562275/af567765-1c3a-4e8b-bebf-08d1a656a995)

![Screenshot (672)](https://github.com/Swateya03/Dashtoon_Generative_AI_Assignment_SWATEYA/assets/142562275/c27fda5e-056f-4cee-a8e5-1fff0e656f2b)

## Methodology

The heart of our approach lies in the efficient modification introduced to classic Gram matrix-based style transfer optimization. By incorporating color-aware considerations, we achieve superior results that not only reflect the desired style but also maintain the semantic content of the source image. This Color-Aware Multi-Style Transfer method enables users to manually select color associations between the target style and content image, providing a flexible and personalized artistic experience.


# Getting Started

## Style Transfer Parameters and Configuration

Configure the style transfer parameters and settings by modifying the following variables in the code:

- `STYLE_IMAGE`: Path to the style image file.
- `CONTENT_IMAGE`: Path to the content image file.

**Style Transfer Configuration:**

- `SMOOTH`: Boolean, whether to apply smoothing during style transfer.
- `SHOW_MASKS`: Boolean, whether to display masks during the process.
- `DEVICE`: Device for computation, automatically set to "cuda" if available, else "cpu".
- `SELECT_MATCHES`: Boolean, set to True to select color correspondences in palettes.
- `EPS`: Small value to prevent division by zero.
- `SIGMA`: Value for sigma in style transfer, typically 0.25 or 0.3.
- `PALETTE_SIZE`: Size of the color palette.
- `ADD_BLACK_WHITE`: Boolean, whether to add black and white colors to the palette.
- `STYLE_LOSS_WEIGHT`: Weight for style loss in the total loss calculation.
- `CONTENT_LOSS_WEIGHT`: Weight for content loss in the total loss calculation.
- `COLOR_DISTANCE`: Distance metric for color matching, options: 'chroma_L2', 'L2'.
- `STYLE_FEATURE_DISTANCE`: Feature distance metric for style, options: 'L2', 'COSINE'.
- `CONTENT_FEATURE_DISTANCE`: Feature distance metric for content, options: 'L2', 'COSINE'.
- `OPTIMIZER`: Optimization algorithm, options: 'LBFGS', 'Adam', 'Adagrad'.
- `LR`: Learning rate for optimization.
- `ITERATIONS`: Number of iterations for style transfer.
- `IMAGE_SIZE`: Desired size of the output image.

**Image Size and Depth Layers:**

- `imsize`: Desired size of the output image.
- `content_layers_default`: List of default layers for content loss computation.
- `color_aware_layers_default`: List of default layers for color awareness in style transfer.

## Image Processing and Color Manipulation Functions

The code includes various functions for image processing and color manipulation. These functions contribute to the overall style transfer process and can be explored for customization.

## ColorPixels Class for Image Pixel Analysis

The `ColorPixels` class facilitates pixel analysis of an input image, automatically converting it into the `np.float32` format. The class provides methods for extracting pixel values in different color spaces, including RGB and Lab.

## 3D Color Histograms Implementation

The `Hist3D` class is designed for the implementation of 3D color histograms, providing functionality to compute and analyze color distributions in an image.

## CreateMask Module for Style Transfer

The `CreateMask` class is a PyTorch module for generating masks based on a given color palette. This module is used in style transfer to create masks that highlight regions in the input image corresponding to specific colors in the palette.

## Gram Matrix Calculation

The `gram_matrix` function computes the Gram matrix for a given input tensor. In the context of neural style transfer, the Gram matrix is used to capture style information from feature maps.

## Masked Gram Matrix Calculation

The `masked_gram_matrix` function computes a masked Gram matrix for a given input tensor and a set of masks. This function is particularly useful in neural style transfer with masked style representations.

## Content Loss Calculation

The `ContentLoss` class computes the content loss between the input features and a target representation. This loss is commonly used in neural style transfer to ensure that the generated image maintains the content of the original content image.

## Custom Functions for Neural Style Transfer

The code includes custom functions such as cosine similarity calculation and setting requires grad, contributing to the neural style transfer implementation.

## ColorAwareLoss Class for Style Loss Calculation

The `ColorAwareLoss` class is a custom loss module for calculating the style loss in the context of color-aware neural style transfer. It provides a color-aware style loss metric, considering both feature information and color masks.

## Normalization Class for Image Preprocessing in Neural Networks

The `Normalization` class is designed as a module to normalize input images, facilitating their integration into a neural network pipeline. It ensures that input images adhere to a standardized format before being fed into a neural network.

## Style Model and Losses Setup

The `get_style_model_and_losses` function sets up the style transfer model along with content and color-aware style losses. It returns a tuple containing the style transfer model, a list of content losses, and a list of color-aware style losses.

## Style Transfer Execution

Use the `run_style_transfer` function to execute the neural style transfer process. It optimizes the input image to blend the content and style images, considering color-aware style information.

## Image Loader and Preprocessing

This section of the code handles the loading and preprocessing of style and content images. It uses the torchvision library to compose a set of transformations such as resizing and converting to tensors. Additionally, color palettes are generated for both images.

## Output Visualization and Saving

The stylized output image is visualized and saved as 'output.png'. 


