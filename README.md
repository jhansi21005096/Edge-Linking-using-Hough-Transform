# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

Developed by : K.Jhansi

Ref no : 212221230045
## Program:

# Read image and convert it to grayscale image
```
import cv2

import matplotlib.pyplot as plt

import numpy as np

img=cv2.imread("half_bridge.jpg")

img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

plt.imshow(img1)

plt.title("Original Image")

plt.show()

gray1=cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)

plt.imshow(gray1)

plt.imshow(gray1,cmap="gray")

plt.title("Gray image")

plt.show()
```

# Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray1,120,150)

plt.figure(figsize=(15,15))

plt.subplot(1,2,1)

plt.imshow(gray1)

img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

plt.imshow(img1)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(canny)

plt.title("Canny Edge Detector")

plt.axis("off")

plt.show()
```


# Detect points that form a line using HoughLinesP
```
lines = cv2.HoughLinesP(canny,1,np.pi/180,threshold = 80,minLineLength=50,maxLineGap = 250) 

```
# Draw lines on the image
```
for line in lines:

    x1,y1,x2,y2 = line[0]
    
    cv2.line(img1,(x1,y1),(x2,y2),(0,255,0),3)

```
# Display the result
```
plt.imshow(img1)

plt.title("Hough Transform")

plt.axis("off")

plt.show()
```
## Output

### Input image and grayscale image
![output(https://github.com/jhansi21005096/Edge-Linking-using-Hough-Transform/blob/main/output1.png)

### Canny Edge detector output
![output(https://github.com/jhansi21005096/Edge-Linking-using-Hough-Transform/blob/main/output2.png)

### Display the result of Hough transform
![output(https://github.com/jhansi21005096/Edge-Linking-using-Hough-Transform/blob/main/output3.png)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
