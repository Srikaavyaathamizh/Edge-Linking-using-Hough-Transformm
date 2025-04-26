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
![image](https://github.com/user-attachments/assets/90ec1a21-1e25-4869-9b8c-f350ce24513d)

### Input image and grayscale image
![image](https://github.com/user-attachments/assets/c9e14486-a61c-4cd5-a5ff-553a283a9005)

### Canny Edge detector output
![image](https://github.com/user-attachments/assets/091ce5c0-d58e-4e38-875b-ff23e31935bf)

### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/b2c10061-1f4d-4545-9e1f-df236600d07d)
