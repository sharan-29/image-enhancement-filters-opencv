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

## Name: Sharan Kumar G 
### Register No: 212224230260  

### Smoothing Filters

## Averaging filter 
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("birds.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
### Weighted averaging
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
### Gaussian filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
### Median filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
###  Sharpening Filters
### Laplacian kernel
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
### Laplacian operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```


###  Output

### Smoothing Filters

- Averaging filter produces blurred image  
<img width="907" height="551" alt="image" src="https://github.com/user-attachments/assets/19e6da52-e371-466a-8017-5de9e3922562" />


- Weighted averaging provides smoother result with less distortion
<img width="672" height="411" alt="image" src="https://github.com/user-attachments/assets/e541b7d4-7ecd-4117-a7e7-e50b251410ec" />


- Gaussian filter preserves edges better while reducing noise  
<img width="645" height="398" alt="image" src="https://github.com/user-attachments/assets/b67471eb-c5d9-4af2-bfa7-8ee621a295a7" />


- Median filter removes salt-and-pepper noise effectively  
<img width="902" height="563" alt="image" src="https://github.com/user-attachments/assets/5d5af639-7856-4b4a-a16c-ff190e8fbd3f" />



###  Sharpening Filters

- Laplacian kernel enhances edges and fine details  
<img width="640" height="407" alt="image" src="https://github.com/user-attachments/assets/2e8faee8-105a-411e-91d0-0774edf8dd9d" />

- Laplacian operator detects edges clearly in grayscale  
<img width="647" height="403" alt="image" src="https://github.com/user-attachments/assets/4c798bbc-3038-4cfb-8b7c-5ff093659f7d" />


---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
