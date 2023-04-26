# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

## Step 1:
Load the necessary packages.

## Step 2:
Read the Image and convert to grayscale.

## Step 3:
Use Global thresholding to segment the image.

## Step 4:
Use Adaptive thresholding to segment the image.

## Step 5:
Use Otsu's method to segment the image.

## Step 6:
Display the results.

## Program

```
import cv2
import matplotlib.pyplot as plt 
from google.colab.patches import cv2_imshow
from cv2 import cvtColor

image=cv2.imread("r1.jpg")
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("r1.jpg",0)
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
    plt.figure(figsize=(5,5))
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
![image](https://user-images.githubusercontent.com/94165326/234523214-2092335d-741f-450e-b0cb-62691b7fdf3a.png)


### Global Thresholding
![image](https://user-images.githubusercontent.com/94165326/234523348-cf566dd6-2fe4-49c0-b15e-c1a49c71ebb0.png)

### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/94165326/234523444-c0245313-4dc2-4d32-a8e7-a1f501074187.png)

### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/94165326/234523525-2093d825-7d84-46c7-a51c-243ec7e34d0d.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

