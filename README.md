# EXP-3-Record-Histogram-processing-
Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image
Plot histogram of the grayscale image
Apply histogram equalization on grayscale image
Read and display a color image
Plot histogram of B, G, R channels
Convert image to HSV color space
Apply histogram equalization on the Value (V) channel
Convert the enhanced image back to BGR format
Display original and enhanced images with histograms
Software Used:
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
Algorithm:
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the image parrot.jpg in grayscale format.

Step 3:
Display the grayscale image and plot its histogram.

Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6:
Read the same image in color format.

Step 7:
Split the image into B, G, R channels and plot their histograms.

Step 8:
Convert the image from BGR to HSV color space.

Step 9:
Apply histogram equalization on the V (Value) channel.

Step 10:
Merge the channels and convert the image back to BGR format.

Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

Developed By:
Name: DEEPIKA V

Register No: 21222420030

Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread(r"myimage.png",cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```

```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

```
```

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
img = cv2.imread('myimage.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```



Output:
ORIGINAL IMAGE:

<img width="337" height="421" alt="image" src="https://github.com/user-attachments/assets/9fb7e24c-ebb3-4aea-87ae-3fe2e2b5bb3e" />

<img width="661" height="427" alt="image" src="https://github.com/user-attachments/assets/41f2270b-1271-4747-8322-e002d8de9bc9" />

Equalised Histogram:

<img width="626" height="424" alt="image" src="https://github.com/user-attachments/assets/5bc31aa2-5dcb-4163-b768-b5ed1c333b49" />

<img width="302" height="424" alt="image" src="https://github.com/user-attachments/assets/9cdd27c5-8693-4a63-a54b-a2d4874f63c0" />

Histogram Equalization of Grayscale Image:

<img width="670" height="251" alt="image" src="https://github.com/user-attachments/assets/89fa8866-fd1c-4014-bf44-c5323dc71518" />


<img width="679" height="233" alt="image" src="https://github.com/user-attachments/assets/e370fd1b-f3d5-4e05-a5fb-d4066fb1e461" />

