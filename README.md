# Optimizing Skin Cancer Detection Neural Networks: SVD for Storage Reduction and Model Pruning for Compute Efficiency

## Introduction

This project aims to optimize neural networks for skin cancer detection by leveraging Singular Value Decomposition (SVD) for image compression and model pruning techniques to enhance compute efficiency. The methodology involves compressing images using SVD, analyzing image quality metrics at various values of `k`, selecting the best reconstruction value, and subsequently proposing and training multiple neural network architectures. These models are pruned iteratively to minimize model size and learnable parameters, making them suitable for deployment in resource-constrained environments.


## Methodology

### 1. Singular Value Decomposition (SVD) for Image Compression

#### Algorithm
1. **Load Image**: Load the Image
   
2. **Apply SVD**: SVD is applied to the images to decompose them into singular vectors and singular values.

3. **Select `k` Components**: Varying numbers of singular values (`k`) are selected to reconstruct the images.

4. **Reconstruct Images**: Images are reconstructed using the selected `k` components.

5. **Evaluate Image Quality Metrics**: Metrics such as RMSE, PSNR, SSIM, VOI, and others are calculated to evaluate the quality of reconstructed images.

6. **Select Optimal `k`**: The `k` value yielding the best trade-off between compression rate and image quality is chosen.

### 2. Neural Network Architecture Proposal and Training

#### Architecture Selection
- Multiple neural network architectures are proposed and trained using the reconstructed images from SVD.

#### Baseline Model
- A baseline model is established to benchmark the performance of subsequent pruned models.

### 3. Model Pruning for Compute Efficiency

#### Pruning Methodology
- **Model Description** - Model contain Text branch and Image branch , we reduce Image Model only since our SVD Reconstructed Data introduces inter-pixel redundancy and psycho visual redundancy making it easier to identify in less amount of conv filters
- **Iterative Pruning**: Filters in convolutional layers and dense layers connected to them are pruned iteratively.
- **Pruning Factors**: Models are pruned by factors such as 50%, 33.33%, 16.5%, until a minimal model with optimized efficiency is achieved.

#### Benefits of Pruning
- Reduces the number of learnable parameters and model size.
- Enhances computational efficiency, making the models suitable for deployment in small-scale environments.

  #### Final Outcome

  - Optimized storage by 73.5% and compression ratio of 3.77 without loss in Information
  - Reduced learnable parameters by 95% and size from 444MB to less than 5 MB
  - This results in less training time and inference time making it efficient to be deployed in resource constrained environments

## Conclusion

By combining SVD for image compression and model pruning for compute efficiency, this project aims to optimize skin cancer detection neural networks. The approach improves storage and computational efficiency b. The findings and methodologies presented here are crucial for deploying effective and efficient skin cancer detection systems in real-world scenarios.

