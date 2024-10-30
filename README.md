# Edge-Linking-using-Hough-Transformm->
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

## PROGRAM
```
DEVELOPED BY :ABISHEK PV
REG NO: 212222230003
```

### Input image 
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('luffy.jpg') 
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```

### Output
![Screenshot 2024-10-30 103103](https://github.com/user-attachments/assets/c47a80bf-78db-4dbd-9adc-76b28e373c93)

### Grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image,
cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
### Output
![Screenshot 2024-10-30 103111](https://github.com/user-attachments/assets/a2fc3e25-5ab8-450e-9299-03dee11031f8)

### Canny Edge detector output
```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
### Output
![Screenshot 2024-10-30 103116](https://github.com/user-attachments/assets/47766dde-42af-41fd-bdca-e300335f3307)

### Display the result of Hough transform
```
lines = cv2.HoughLinesP(canny_edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=100, maxLineGap=100)
output_image = image.copy()
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
### Output
![Screenshot 2024-10-30 103120](https://github.com/user-attachments/assets/d04a3416-afc2-4939-8988-f688e8bf54ba)


## Result
Thus,The Python program to detect the lines using Hough Transform run successfully.
