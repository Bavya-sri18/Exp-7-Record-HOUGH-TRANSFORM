# Exp-7-Record-HOUGH-TRANSFORM

## NAME : BAVYA SRI B
## REG.NO : 212224230034

## Aim 

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective

Understand each stage of image processing

Learn how to build a complete computer vision pipeline

Practice writing code in guided sections

## Software Used

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Program

```PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread(r"D:\Screenshots\Bavya.jpeg")

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

## Original image

<img width="682" height="530" alt="image" src="https://github.com/user-attachments/assets/00a7f30e-bfe5-46b1-9e1f-cbc6113abbe2" />

## Grayscale image

<img width="685" height="537" alt="image" src="https://github.com/user-attachments/assets/bba1bde2-490c-475d-af0c-768a1e051206" />

## Canny Edge Detector image

<img width="687" height="535" alt="image" src="https://github.com/user-attachments/assets/847b9584-eee3-4b2c-a645-e7eccb3e3bae" />

## Hough Transform image

<img width="686" height="542" alt="image" src="https://github.com/user-attachments/assets/b6f4437a-1cf9-47a9-942e-705411b96a0d" />

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
