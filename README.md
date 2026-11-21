# EXP. 8 – THRESHOLDING USING OPENCV

**NAME:** THARSHINI.M
**REG NO:** 212224230287

## Aim

To implement different thresholding techniques using OpenCV and Python to segment an image into foreground and background regions.

## Software Requirements

- Python
- Anaconda
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Thresholding Techniques

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the input image into grayscale using `cv2.cvtColor()`.
4. Display the original image.
5. Apply Global Thresholding using `cv2.threshold()` with a threshold value of 127.
6. Apply Adaptive Thresholding using the Gaussian method.
7. Apply Otsu's Thresholding to automatically determine the optimal threshold value.
8. Display all the thresholded images separately.
9. Compare the results of different thresholding techniques.

## Implementation

### 1. Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### 2. Read and Convert the Image

```python
image = cv2.imread('Image.png')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

### 3. Display Original Image

```python
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```

**OUTPUT:**

<img width="136" height="197" alt="image" src="https://github.com/user-attachments/assets/fb5e4c91-d570-4d55-8a0d-e326178138ea" />


### 4. Global Thresholding

```python
_, global_thresholded = cv2.threshold(
    gray_image, 127, 255, cv2.THRESH_BINARY
)

plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```

**OUTPUT:**

<img width="194" height="202" alt="{E6752F89-E0CC-4E86-94BA-1CF1B88B2CCD}" src="https://github.com/user-attachments/assets/087ceb7b-7a48-4154-9e2a-c435b7f8be33" />


### 5. Adaptive Thresholding

```python
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```

**OUTPUT:**

  <img width="189" height="232" alt="{D171928A-FDE7-401A-90D2-E6D4301ACE3C}" src="https://github.com/user-attachments/assets/a32e3991-170a-4efd-9ffa-c743350d8c34" />


### 6. Otsu's Thresholding

```python
_, otsu_thresholded = cv2.threshold(
    gray_image, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```

**OUTPUT:**

<img width="165" height="194" alt="image" src="https://github.com/user-attachments/assets/f8322e59-5a8e-4d4d-92b2-0694ff5018e7" />


### 7. Display All Outputs

```python
plt.tight_layout()
plt.show()
```

## Result

Thus, Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques were successfully implemented using OpenCV and Python to segment the input image.
