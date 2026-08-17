# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

- **Name:** LAAVANYA R
- **Register No:** 212224230135 

---
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("lotus.jpg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
plt.show()
```
1.Averaging Filter:
```
avg = cv2.blur(img, (5,5))
plt.imshow(avg)
plt.title("Averaging Filter")
plt.axis("off")
plt.show()
```
2.Weighted Averaging Filter:
```
kernel = np.array([[1,2,1],
                 [2,4,2],
                 [1,2,1]], np.float32) / 16
weighted = cv2.filter2D(img, -1, kernel)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()

```
3.Gaussian Filter:
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()

```
4.Median Filter:
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
5.Laplacian Sharpening (Kernel):
```
kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
6.Laplacian Operator:
```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```



##  Output

### Smoothing Filters

- Averaging filter produces blurred image  
- Weighted averaging provides smoother result with less distortion  
- Gaussian filter preserves edges better while reducing noise  
- Median filter removes salt-and-pepper noise effectively  

###  Sharpening Filters

- Laplacian kernel enhances edges and fine details  
- Laplacian operator detects edges clearly in grayscale  

---
<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/7ad9b87a-01ea-483c-b913-5e47e89aa3a8" />


<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/3f90fdd2-4d64-4b0f-968e-3160e453cf5c" />


<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/83bc2e22-a19c-45b1-93ff-dd7d05108eb5" />




<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/3c383c7a-d2b2-4d8c-8044-8089f786e170" />


<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/809d1940-1cd3-4f76-bc60-63992d17d188" />




<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/c3540182-0db6-403b-8ee8-63d429a65a1b" />


<img width="515" height="358" alt="download" src="https://github.com/user-attachments/assets/ba0e0b38-41b4-4176-9623-3452c3a7f123" />



##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
