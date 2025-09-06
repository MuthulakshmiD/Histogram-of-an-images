# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().


### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:

### Developed By: Muthulakshmi D
### Register Number: 212223040122
```
import matplotlib.pyplot as plt
import cv2

# Load images
grayscale_image = cv2.imread("4.jpeg", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("4.jpeg")

# Compute histograms
gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])

# Display images
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(grayscale_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')

plt.show()

# Display histograms
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.plot(gray_hist, color='black')
plt.title("Grayscale Image Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")

plt.subplot(1, 2, 2)
plt.plot(hist_r, color='red', label='Red Channel')
plt.plot(hist_g, color='green', label='Green Channel')
plt.plot(hist_b, color='blue', label='Blue Channel')
plt.title("Color Image Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.legend()

plt.show()

# Histogram equalization of grayscale image
equalized_gray_img = cv2.equalizeHist(grayscale_image)

plt.figure(figsize=(8,5))
plt.imshow(equalized_gray_img, cmap='gray')
plt.title("Equalized Grayscale Image")
plt.axis('off')
plt.show()

# Histogram of equalized grayscale image
plt.figure(figsize=(8,5))
plt.plot(cv2.calcHist([equalized_gray_img], [0], None, [256], [0,256]), color='black')
plt.title("Histogram of Equalized Grayscale Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.show()

```
## Output:
### Input Grayscale Image and Color Image

<img width="1253" height="400" alt="image" src="https://github.com/user-attachments/assets/368b630b-eaa5-4061-b01f-d2419b1d99ac" />


### Histogram of Grayscale Image and any channel of Color Image

<img width="1296" height="611" alt="image" src="https://github.com/user-attachments/assets/c40483a2-94cc-4211-95c1-a1b9d450f40c" />


### Histogram Equalization of Grayscale Image.

<img width="886" height="553" alt="image" src="https://github.com/user-attachments/assets/25c66374-9589-4f6b-bb54-8559c23bdd1d" />

<img width="908" height="615" alt="image" src="https://github.com/user-attachments/assets/f7a641ff-3011-4903-9e09-246da3a3f624" />


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
