# Color-Aware Multi-Style Transfer

Image style transfer is a widely explored technique that manipulates the appearance of a source image, known as the "content" image, to reflect the texture and colors of a target "style" image. While Gram matrix-based optimization has been a popular approach for style transfer, it often lacks consideration for the correlation between colors and styles. This becomes challenging, especially when dealing with target style images that exhibit multiple style types.

## Overview

In this work, we introduce a Color-Aware Multi-Style Transfer method to address the limitations of classic Gram matrix-based optimization. Our approach preserves the style-color correlation between style and generated images, leading to aesthetically pleasing and semantically meaningful results. A notable feature of our method is the ability for users to manually select color associations between the target style and content image, providing enhanced transfer flexibility.

## Key Contributions

- **Color-Aware Optimization:** We propose an efficient modification to the traditional Gram matrix-based style transfer optimization, incorporating color-aware considerations for improved results.
- **Multi-Style Transfer:** Our method accommodates images with multiple styles, offering a simple yet effective solution for diverse artistic preferences.
- **User Flexibility:** By allowing manual color associations, users can tailor the style transfer process to achieve their desired artistic outcomes.

## Validation and Results

We validated our Color-Aware Multi-Style Transfer method through qualitative comparisons, including a user study with 30 participants. The results demonstrate the simplicity, ease of implementation, and visually appealing outcomes, especially when dealing with images exhibiting multiple styles.

## Source Code

The source code for our method is available on [GitHub](https://github.com/mahmoudnafifi/color-aware-style-transfer).

## Getting Started

To get started with our Color-Aware Multi-Style Transfer, please refer to the provided source code and follow the instructions in the repository.

---

**Note:** This introduction provides a general overview. For detailed information, methodology, and results, please refer to the complete documentation and research paper.
