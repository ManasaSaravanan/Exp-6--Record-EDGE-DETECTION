# EDGE-DETECTION
# MANASA S
# 212224220059
## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

**Developed By:** MANASA S

**Register Number:** 212224220059

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sv.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

## Output

### Input Image 

<img width="356" height="492" alt="image" src="https://github.com/user-attachments/assets/98cb8dd3-b6f1-47c1-8170-4cf9dcca361b" />


### 1. Sobel Edge Detector

<img width="348" height="501" alt="image" src="https://github.com/user-attachments/assets/0deeee42-2443-45c4-9583-b35b867c688f" />


### 2. Laplacian Edge Detector

<img width="363" height="497" alt="image" src="https://github.com/user-attachments/assets/b8a00c8f-8dee-4e79-a9cd-7039c1313c76" />


### 3. Canny Edge Detector

<img width="356" height="493" alt="image" src="https://github.com/user-attachments/assets/7edf79ae-184b-459c-b173-ad3493fe477b" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
