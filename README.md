
### Residual U-Net Autoencoder for Scan Noise Removal
This project implemented a custom Residual U-Net Autoencoder to effectively remove scan noise from PDF images, ensuring improved readability and visual quality of processed documents.
Trains a supervised Residual UNET AutoEncoder to take non-digital born PDF image scans (from before 1980s) and remove the scan noises/artifacts from them.  
NOTE: The project started as a diffusion model but was later refactored to use a RESIDUAL UNET for simplicity. See initial attempt in the repo


**Image Preprocessing and Dataset Preparation**  
- Developed an image preprocessing pipeline to handle noisy and clean image pairs, including splitting images into fixed-size patches using a custom sliding window technique.  
- Applied efficient padding methods and stitching mechanisms to seamlessly reconstruct large images from predicted patches.  
- Created a robust dataset of ~20000 image patches for training and evaluation, leveraging techniques like histogram equalization to enhance feature representation.

**Custom Residual U-Net Architecture**  
- Designed a Residual U-Net model featuring downsampling and upsampling blocks with skip connections for preserving spatial context.  
- Integrated custom residual blocks to improve learning efficiency by mitigating the vanishing gradient problem.  
- Leveraged convolutional layers with batch normalization and ReLU activation for robust feature extraction.  

**Loss Functions and Training**  
- Implemented a multi-objective loss function combining Structural Similarity Index (SSIM), Mean Squared Error (MSE), and edge preservation losses to optimize the model for document-specific noise removal.  
- Trained the model using TensorFlow and mixed-precision techniques, utilizing gradient clipping to ensure stable convergence across 100 epochs.  
- Achieved significant performance improvements, with the model demonstrating high fidelity in restoring text and image quality.  

**Efficient Prediction Pipeline**  
- Built an end-to-end prediction system capable of processing and denoising large test images in real-time.  
- Used a patch-based prediction approach, enabling the model to handle high-resolution images without exceeding memory limits.  
- Implemented real-time visualization of input, predicted, and target images to validate and analyze the model’s performance.

**Tools and Technologies**  
- Leveraged TensorFlow for model training and optimization, with NumPy and OpenCV for preprocessing and patch management.  
- Used Matplotlib and Streamlit for visualization and user interaction.  
- Applied advanced RAG techniques to enhance model usability in document processing applications.

**Impact and Future Work**  
- This project demonstrates the potential of Residual U-Nets for noise removal in scanned documents, making it suitable for use in digitization and archival systems.  
- Plans include the following ...
         -- extending the model to handle color images,
         -- optimizing inference speed
         -- further finetuning to generalize the model for more variations in scan noises 
         -- deploying the solution as an API for seamless integration with document management systems.
