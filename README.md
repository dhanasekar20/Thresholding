# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("white.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("white.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Otsu's method to segment the image 
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Adaptive thresholding to segment the image
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## OUTPUT:

### Original Image and Grayscale Image

![image](https://user-images.githubusercontent.com/75235293/169637308-1ff3f9dc-2439-43c3-890f-3467a67c5fe5.png)


### Global Thresholding
![image](https://user-images.githubusercontent.com/75235293/169637371-bac5a031-4ebd-466a-ba9d-f869080e68f6.png)
![image](https://user-images.githubusercontent.com/75235293/169637380-52fda1c5-2798-4a2f-b6ff-941fd2f15c93.png)


![image](https://user-images.githubusercontent.com/75235293/169637387-268f8b99-1398-4aff-a4e9-2b7e8a89644e.png)


![image](https://user-images.githubusercontent.com/75235293/169637413-01a08103-279c-4309-98e2-ce4adbd707fc.png)
![image](https://user-images.githubusercontent.com/75235293/169637442-e9efe14d-cfcc-4dfa-9403-b812f122d4d8.png)


### Adaptive Thresholding

![image](https://user-images.githubusercontent.com/75235293/169637501-a976f691-6b36-449d-a5c5-c9d6e060de64.png)


![image](https://user-images.githubusercontent.com/75235293/169637509-76d0b4b1-596d-4d9f-a351-bab86adbc6bb.png)


### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/75235293/169637474-eac74d3a-ed4b-4401-87bd-4f00b5bc33b5.png)


## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

