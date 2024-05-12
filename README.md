# EX 10 IMPLEMENTATION OF OPENING AND CLOSING
## DATE:
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation
 
## Program:
```
Developed by : SHABREENA VINCENT
Register no : 212222230141
```
## Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
## Create the Text using cv2.putText
```
# Read the color image
input_image_path = 'Dhoni.jpg'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 100, 200)  # you can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Perform opening
opening = cv2.morphologyEx(edges, cv2.MORPH_OPEN, kernel)

# Perform closing
closing = cv2.morphologyEx(edges, cv2.MORPH_CLOSE, kernel)
```


## Create the structuring element
```
plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
```


## Use Opening operation
```
plt.subplot(2, 3, 2)
plt.imshow(opening, cmap='gray')
plt.title('Opening')
plt.axis('on')
```



## Use Closing Operation
```
plt.subplot(2, 3, 3)
plt.imshow(closing, cmap='gray')
plt.title('Closing')
plt.axis('on')

plt.show()

```
## Output:
### Display the input Image


![Untitled](https://github.com/kancharlaNarmadha/OPENING--AND-CLOSING/assets/119559316/c8ab8108-dd4a-4ec8-a421-463a2758065d)


### Display the result of Opening

![Untitled](https://github.com/kancharlaNarmadha/OPENING--AND-CLOSING/assets/119559316/f7ed60fd-0830-4684-a1e8-bd626c8a8d22)



### Display the result of Closing

![Untitled](https://github.com/kancharlaNarmadha/OPENING--AND-CLOSING/assets/119559316/1b0d33bd-2a96-4915-b860-3b602878d054)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
