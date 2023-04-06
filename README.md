### Histogram and Histogram Equalization of an image
### Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

### Software Required:
Anaconda - Python 3.7

### Algorithm:
### Step1:
Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().

### Step2:
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.

### Step3:
Plot the image and its stem plots using the plt.show() and plt.stem() functions.

### Step4:
Equalize the grayscale image using the in-built function cv2.equalizeHist().

### Step5:
Print the original and equalized image using cv2.imshow() and end the program.

### Program:
```
### Developed By: Vishwa Rathinam S
### Register Number:212221240063
import cv2
import matplotlib.pyplot as plt
```
### Write your code to find the histogram of gray scale image and color image channels.
```

import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("gray.jpg")
clr_image = cv2.imread("color.jpg",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",clr_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Display the histogram of gray scale image and any one channel histogram from color image
```


import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("gray.jpg")
clr_image = cv2.imread("color.jpg",-1)
gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
clr_hist = cv2.calcHist([clr_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(clr_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(clr_hist)
plt.show()

```
### Write the code to perform histogram equalization of the image. 
```
import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("gray.jpg",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
### Input Grayscale Image and Color Image:
![Screenshot (2)](https://user-images.githubusercontent.com/95266350/230277463-b5063fdf-fa4f-424c-8dcc-5205ed6dd7bc.png)

### Histogram of Grayscale Image and any channel of Color Image:
![Screenshot_20230406_102851](https://user-images.githubusercontent.com/95266350/230277825-02ef973a-2d6d-4779-8617-cb9966ac062c.png)
![Screenshot_20230406_102910](https://user-images.githubusercontent.com/95266350/230277847-b8051a0b-d22b-482c-aba3-ec504b248cc5.png)


### Histogram Equalization of Grayscale Image:
![Screenshot (3)](https://user-images.githubusercontent.com/95266350/230277877-6700c7ef-f66f-4165-b0d5-51feaead551f.png)


### Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
