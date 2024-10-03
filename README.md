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
```python
# Developed By: priyadharshini 
# Register Number: 212223230159

import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread(r"C:\Users\admin\Downloads\gray--gray.jpg", cv2.IMREAD_GRAYSCALE)  
color_image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg") 
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Color Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
```
import cv2
import matplotlib.pyplot as plt

gray_image = cv2.imread(r"C:\Users\admin\Downloads\gray--gray.jpg", cv2.IMREAD_GRAYSCALE)  
color_image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg") 

gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
color_hist = cv2.calcHist([color_image], [0], None, [256], [0, 256])

plt.figure(figsize=(12, 6))

plt.subplot(1, 2, 1)
plt.title("Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(gray_hist, color='black')

plt.subplot(1, 2, 2)
plt.title("Color Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(color_hist, color='blue')

plt.tight_layout()
plt.show()

```
```
import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread(r"C:\Users\admin\Downloads\gray--gray.jpg", cv2.IMREAD_GRAYSCALE)
color_image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg")
resized_gray_image = cv2.resize(gray_image, (500, 400))
equalized_image = cv2.equalizeHist(gray_image)
cv2.imshow("Original Grayscale Image", gray_image)
cv2.waitKey(0)

cv2.imshow("Resized Grayscale Image", resized_gray_image)
cv2.waitKey(0)
cv2.imshow("Equalized Grayscale Image", equalized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

plt.figure()

plt.subplot(1, 2, 1)
plt.title("Original Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
plt.plot(gray_hist)

plt.subplot(1, 2, 2)
plt.title("Equalized Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
equalized_hist = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])
plt.plot(equalized_hist)

plt.tight_layout()
plt.show()


```

## Output:
### Input Grayscale Image and Color Image

![image](https://github.com/user-attachments/assets/06168e46-f911-42e5-9a1c-79cab584f2d3)

![image](https://github.com/user-attachments/assets/4360cedb-c62d-496b-9521-94e7fcdf0097)



### Histogram of Grayscale Image and any channel of Color Image

![image](https://github.com/user-attachments/assets/3ac619ea-8423-4f40-949d-142505ab3874)


### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/d7037ea3-a542-4b32-af98-76b52b23445e)


![image](https://github.com/user-attachments/assets/2ec3bb30-03c2-414b-b8e0-03bbe12dd54e)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
