# Histogram-of-an-images

# **Name:** SANTHOSH G

# **Register Number:** 212225100044


## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** SANTHOSH G

**Register Number:** 212225100044

python

### Step1 : Histogram Equalization for Grayscale Images

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('eagle.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Step2 : Histogram Equalization for Color Images

```python
img = cv2.imread('eagle.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```




## Output

### Input Grayscale Image

<img width="449" height="305" alt="image" src="https://github.com/user-attachments/assets/80c53cc0-5296-4699-966b-dec9b842d754" />


### Input Grayscale Image Range

<img width="491" height="304" alt="image" src="https://github.com/user-attachments/assets/6e52c416-f50a-4629-9799-95bc5c3ae7f2" />


### Input Grayscale Image Equalized Histogram

<img width="565" height="330" alt="image" src="https://github.com/user-attachments/assets/477b9538-793d-4432-b6d8-1f79806e004d" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="467" height="314" alt="image" src="https://github.com/user-attachments/assets/593daa8c-403d-4c25-b0c8-aea0ee99d6bc" />


### Equalized Image

<img width="509" height="304" alt="image" src="https://github.com/user-attachments/assets/9179b6a7-45ec-4c5b-82b6-c3052dd6d276" />


### Equalized Histogram

<img width="476" height="307" alt="image" src="https://github.com/user-attachments/assets/97e800c7-cecd-4d63-8813-6e0f996d49d3" />


### Final Output of Original Image and Equalized 

<img width="752" height="272" alt="image" src="https://github.com/user-attachments/assets/740eabf9-85ae-4b33-9580-1887e14c0018" />


### Final Output of Original Image and its Histogram Equalized

<img width="745" height="254" alt="image" src="https://github.com/user-attachments/assets/e02f1b40-609c-4854-b225-37cb10b99169" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
