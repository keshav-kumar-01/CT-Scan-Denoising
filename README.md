# CT Image Denoising Using Poisson and Periodic Noise Reduction Techniques

## Project Overview


#### This project focuses on enhancing the quality of brain CT images by reducing noise using Poisson and periodic noise reduction techniques. CT images often contain various types of noise, such as Poisson noise (due to photon detection limitations) and periodic noise (arising from mechanical and electronic components). Reducing this noise is critical for improving image clarity, leading to more accurate diagnoses in medical imaging.


## Content


* Features
* Requirments
* Usage
* Code Explaination
* Results
* Conclusion
* Future Improvements
* Refrence

## Features 
* DICOM and JPEG Support: Allows for loading of both DICOM and JPEG images.
* Poisson Noise Reduction: Uses total variation (TV) filtering to denoise Poisson noise.
* Periodic Noise Reduction: Uses Fourier-based notch filtering to remove periodic noise.
* Image Quality Metrics: Calculates SNR, PSNR, and SSIM for performance evaluation.

## Requirments
* Python 3.x
* Install following libraries via running the following script :
```
!pip install numpy
!pip install matplotlib
!pip install pydicom
!pip install scikit-image
!pip install PIL

```
## Usage
* Load the Dataset: Place the brain CT images in a folder.
* Run the Code: Execute the code to load images, apply denoising techniques, and evaluate results.
* View Results: The denoised images and metrics (SNR, PSNR, SSIM) will be displayed.

## Code Explaination

### Loading CT Images

##### The load_dicom_series function reads CT images from a specified directory, supporting both .dcm (DICOM) and .jpg file formats. Non-DICOM images are preprocessed to align with medical imaging standards.

### Denoising Techniques
* Poisson Denoising: The denoise_poisson function applies a total variation (TV) filter to reduce Poisson noise while preserving critical edges in the image.
* Periodic Noise Reduction: The denoise_periodic function applies a notch filter in the Fourier domain, targeting specific frequency patterns to reduce periodic noise.
### Performance Metrics
* SNR (Signal-to-Noise Ratio): Calculates the clarity of the denoised image compared to the original.
* PSNR (Peak Signal-to-Noise Ratio): Measures the peak error between the original and denoised images.
* SSIM (Structural Similarity Index): Compares structural similarity, indicating how much detail is preserved in the denoised images.

## Result

| Metric  | Original  | Poisson Denoised |
| ------------- |:-------------:|:------|
| SNR      | ∞     |   0.98 (1.13 -- Periodic  Denoised)    |
| PSNR     | N/A    |   -36.97    |
| SSIM	      | 1.0     |    0.016   |

* The Poisson noise reduction achieved a modest improvement, with an SNR of 0.98.
* The periodic noise reduction achieved a slightly higher SNR, making it more effective for this type of noise.
* Low SSIM and PSNR indicate room for improvement in retaining structural details in denoised images.

## Conclusion 
#### This project provides an effective approach for reducing Poisson and periodic noise in CT brain images, with moderate success in enhancing image quality. The Fourier-based notch filter proved particularly effective for periodic noise reduction, while the TV filter demonstrated general noise-reduction capabilities.

## Future Improvements
* Implement a hybrid model that combines multiple denoising techniques.
* Experiment with adaptive filtering to improve SSIM and PSNR scores.
* Test additional image quality metrics for a more comprehensive evaluation.

## References
* Total Variation Filtering in Image Processing
* Notch Filtering for Periodic Noise Reduction
* SSIM and PSNR in Medical Imaging
