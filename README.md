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

- **Name:**:Pugazh sozhan.A
- **Register No:** 212224240121

---
##  Output

### Smoothing Filters

- Averaging filter produces blurred image
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("image55.JPEG")
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
- Weighted averaging provides smoother result with less distortion
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```  
- Gaussian filter preserves edges better while reducing noise
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```  
- Median filter removes salt-and-pepper noise effectively  
```
median = cv2.medianBlur(image2, 13)

plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
###  Sharpening Filters

- Laplacian kernel enhances edges and fine details
```kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
- Laplacian operator detects edges clearly in grayscale  
```
laplacian = cv2.Laplacian(image2, cv2.CV_64F)
laplacian = np.absolute(laplacian)
laplacian = np.uint8(laplacian)

plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```

##  Output

### Smoothing Filters
<img width="717" height="251" alt="download" src="https://github.com/user-attachments/assets/88c955db-1cc2-4e9a-a948-4e4f999295a0" />

<img width="515" height="370" alt="download" src="https://github.com/user-attachments/assets/9575e323-b0bf-41f9-8ec7-7d240c9644f9" />

<img width="515" height="370" alt="download" src="https://github.com/user-attachments/assets/66f58f1b-6e48-4409-93a2-787f44a07934" />

<img width="515" height="370" alt="download" src="https://github.com/user-attachments/assets/a0cf823c-77a7-4de1-ab77-4454a1c2b9f7" />







###  Sharpening Filters

<img width="515" height="370" alt="download" src="https://github.com/user-attachments/assets/ad952166-7143-47d4-8dae-13865eb46e13" />

<img width="515" height="370" alt="download" src="https://github.com/user-attachments/assets/b894b9f6-14ce-4237-acb3-39174f6ffdc7" />






##  Result
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.



