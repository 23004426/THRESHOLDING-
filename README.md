# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
# Developed by: Tirupathi Jayadeep
# Register Number: 212223240169
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("dog.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dog.jpg",0)

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
## Output

### Original Image
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/eb654761-7e9e-448a-bb8c-db2f9c634c04)
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/e48e2c51-032f-47d8-bd5f-40bf7f7896d9)
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/f4b0c83e-ad9f-4008-82ef-8cca9d8bb866)
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/8f0c228e-1eb4-4dad-ad30-354ff02b0bff)
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/f56ba5a3-86d8-41d2-9206-8af9581de30d)
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/b43bf5b5-d5a1-440e-8f52-13631864281d)


### Global Thresholding
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/85777404-dfb4-4cb2-9a00-ec9e11863460)


### Adaptive Thresholding
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/7fde7991-c6c8-4d6c-ae51-035414cf4c66)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/23004426/THRESHOLDING-/assets/144979327/0f64f3ce-31c9-4d61-acce-29b84f889777)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
