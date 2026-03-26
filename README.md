# Receipt Image Enhancement for OCR
This project focuses on enhancing receipt images to improve text readability and prepare them for Optical Character Recognition (OCR). The pipeline addresses common issues such as uneven lighting, noise, and low contrast.
## Problem 
Receipt images often suffer from poor lighting conditions, shadows, wrinkles, and background noise, making it difficult to extract text accurately. This project aims to preprocess and enhance receipt images to improve OCR performance.

## Methodology

### Receipt Segmentation
- Applied Otsu Thresholding to separate the receipt from the background
- Used Morphological Closing to fill gaps and remove small holes
- Extracted the largest contour as the receipt region

### Cropping
- Cropped the image to the bounding box of the detected receipt
- Reduced unnecessary background noise

### Background Normalization (Background Division)
- Applied large Gaussian Blur to estimate background illumination
- Divided the original image by the background to normalize lighting

### Wavelet-based Sharpening
- Performed wavelet decomposition (db4, level=3)
- Enhanced horizontal and vertical detail coefficients
- Reconstructed the image to improve text edge clarity

### Noise Reduction
- Applied slight Gaussian Blur to reduce minor noise

### Contrast Enhancement (CLAHE)
- Used CLAHE to improve local contrast and highlight text regions

## Results
- Improved text visibility under uneven lighting conditions
- Reduced background noise and shadow effects
- Enhanced character edges for better OCR readiness

## Tools
- Python
- OpenCV
- NumPy
- Mahotas
- PyWavelets
- Matplotlib (for visualization)
