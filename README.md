# EDGE-DETECTION

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

**Developed By:** SHRIVARSHAN P G

**Register Number:** 212225240146

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

<img width="702" height="420" alt="image" src="https://github.com/user-attachments/assets/1b50e40b-1ab7-4ef9-b026-f6712c43e370" />


### 1. Sobel Edge Detector

<img width="678" height="412" alt="image" src="https://github.com/user-attachments/assets/dfa0bbfa-ad54-4055-ba3a-19ae4fb511ae" />


### 2. Laplacian Edge Detector

<img width="722" height="420" alt="image" src="https://github.com/user-attachments/assets/e0bd1fea-894c-4e16-a8a9-cf8431994161" />


### 3. Canny Edge Detector

<img width="702" height="417" alt="image" src="https://github.com/user-attachments/assets/e7e70f18-c5b7-41f6-81c5-9d42e3ee8925" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
