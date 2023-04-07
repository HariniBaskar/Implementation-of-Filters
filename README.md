# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().


## Program:
```
### Developed By  : Harini.B
### Register Number: 212221230035
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("butterfly (1).jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
1. Smoothing Filters

i) Using Averaging Filter
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")

ii) Using Weighted Averaging Filter
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")

iii) Using Gaussian Filter
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")

iv) Using Median Filter
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")

2. Sharpening Filters
i) Using Laplacian Kernal
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")

ii) Using Laplacian Operator
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")
```


## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![pic1](https://user-images.githubusercontent.com/93427253/230601121-8289d3fb-cb39-4ba3-a38b-65c6b6f84efd.png)

ii) Using Weighted Averaging Filter

![pic2](https://user-images.githubusercontent.com/93427253/230601131-ea08a4c2-1d8e-4bab-9e79-a93e8751f5c0.png)

iii) Using Gaussian Filter

![pic3](https://user-images.githubusercontent.com/93427253/230601146-7cf04958-e9b6-4568-bd8f-55f60cbe2bdd.png)

iv) Using Median Filter

![pic4](https://user-images.githubusercontent.com/93427253/230601160-5948286c-cf90-429a-934c-99b987d2468b.png)

### 2. Sharpening Filters

i) Using Laplacian Kernal

![pic5](https://user-images.githubusercontent.com/93427253/230601252-73ffe4ca-b62f-4267-9ae2-9c9e90a387fd.png)

ii) Using Laplacian Operator

![pic6](https://user-images.githubusercontent.com/93427253/230601266-8008f851-be2e-4e2a-abee-6e7061ce2cd4.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
