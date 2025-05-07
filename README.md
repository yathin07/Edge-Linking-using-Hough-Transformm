# Edge-Linking-using-Hough-Transformm
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

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program
### NAME : YATHIN REDDY T
### REGISTRATION NUMBER : 212223100062

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('7.jpg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output
![image](https://github.com/user-attachments/assets/3dc52c1c-40ba-423f-9e8d-a2e63582e4a8)


### Input image and grayscale image
![image](https://github.com/user-attachments/assets/2483e5e5-6a42-4195-961f-74f044e17887)


### Canny Edge detector output
![image](https://github.com/user-attachments/assets/8e3f56ac-a8fb-417a-8d29-b1c8d9fd8de4)


### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/d4f8b825-e057-44b3-b63d-89b18136f59c)


## RESULT:
Thus the programs are executed successfully.
