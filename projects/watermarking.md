Here's a more professional and polished version of your markdown:

---

# Watermarking Images

The motivation for watermarking images arises from the increasing use of generative AI models, which often create new images based on training or input data that may be protected by copyright.

## Process Overview
1. Embedding invisible watermarks into images
2. Searching for images with potential similarities
3. Detecting invisible watermarks in other images

### 1. Embedding
To embed invisible watermarks effectively, the image is partitioned into blocks. This approach enhances the likelihood of detecting a sufficient number of intact blocks even after transformations such as rotation or cropping. Since the watermarking of each block is independent, the process is highly parallelizable. Additionally, many of the operations involved are matrix-based and can benefit from GPU acceleration.

Two critical constraints must be satisfied:
- **Invisibility:** The watermark must not be perceptible to the human eye.
- **Robustness:** The watermark must withstand common image transformations.

#### 1.1. Extracting the Y-Channel
#### 1.2. Transforming into Frequency-Domain
#### 1.3. Generating and applying Watermark
#### 1.4. Reconstructing the Image

### 2. Search
*Content to be added...*

### 3. Detection
Detecting watermarks in images is computationally intensive, particularly because the original image may have undergone various transformations. However, since time constraints are not a critical factor, an effective approach involves first identifying the block frequency. Once the block frequency is determined, the detection process can treat each block as an independent job. By statistically evaluating the number of detected blocks, it becomes possible to assess whether a watermark is present. In the worst-case scenario, all potential blocks must be examined until a statistically significant detection threshold is reached.

#### 3.1. Transforming the Image
#### 3.2. Correlating the Frequency-Domain