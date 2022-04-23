# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().
<br>

### Step2:
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.
<br>

### Step3:
Plot the image and its stem plots using the plt.show() and plt.stem() functions.
<br>

### Step4:
Equalize the grayscale image using the in-built function cv2.equalizeHist().
<br>

### Step5:
Print the original and equalized image using cv2.imshow() and end the program.
<br>

## Program:
```python
# Developed By: Srinivasan S
# Register Number: 212220230048
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
gray_image = cv2.imread("grayscale.png")
color_image = cv2.imread("colour.png",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Display the histogram of gray scale image and any one channel histogram from color image
gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
color_hist = cv2.calcHist([color_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(color_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()

# Write the code to perform histogram equalization of the image. 
gray_image = cv2.imread("grayscale.png",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows

```
## Output:
### Input Grayscale Image and Color Image
![Gray image](https://user-images.githubusercontent.com/103049243/164911474-4c84e677-b8c7-4904-aa80-0d5b0cad9370.jpg)
![Color image](https://user-images.githubusercontent.com/103049243/164911485-a1b9ea76-0057-4f4a-a6bb-1822c179b6f1.jpg)


### Histogram of Grayscale Image 
![Screenshot 2022-04-23 202708](https://user-images.githubusercontent.com/103049243/164911503-f1a96c40-4cfc-4d3e-b969-aad51d9010c5.png)
![Screenshot 2022-04-23 202800](https://user-images.githubusercontent.com/103049243/164911507-400a20c5-b749-4dd5-8f26-82a710b95986.png) 

### Histogram of Color Image
![Screenshot 2022-04-23 202737](https://user-images.githubusercontent.com/103049243/164911553-6f3b8eb1-a6ba-4db2-bd5e-777c9a0f3e7a.png)
![Screenshot 2022-04-23 202820](https://user-images.githubusercontent.com/103049243/164911582-2167f2aa-c44e-4b16-a697-e8bf73017931.png)

### Histogram Equalization of Grayscale Image
![Screenshot 2022-04-23 202847](https://user-images.githubusercontent.com/103049243/164911593-c45ebe04-0a78-4a3e-9bf6-3b0337ecc9b5.png)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
