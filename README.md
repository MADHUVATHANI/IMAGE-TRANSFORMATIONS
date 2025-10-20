# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.
### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.
### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 2.Scaling resizes the image by scaling factors. 3.Shearing distorts the image along one axis. 4.Reflection flips the image horizontally or vertically. 5.Rotation rotates the image by a given angle.
### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.
### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.
## Program:
```python
#Developed By: MADHUVATHANI V
#Register Number:212223040107

#i)Image Translation
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('a.jpg')
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')

#ii) Image Scaling
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')

#iii)Image shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')

#iv)Image Reflection
reflected_image = cv2.flip(image, 2)  
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')

#v)Image Rotation
(height, width) = image.shape[:2] 
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')

#vi)Image Cropping
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
## Output:
### i)Image Translation
<img width="485" height="404" alt="image" src="https://github.com/user-attachments/assets/aaa4601f-cdc4-4170-88ac-b70ab5e43b19" />

### ii) Image Scaling
<img width="542" height="181" alt="image" src="https://github.com/user-attachments/assets/0bec692d-36e8-4d34-a031-240d3a1e956e" />

### iii)Image shearing
<img width="511" height="405" alt="image" src="https://github.com/user-attachments/assets/6117ddb7-18c7-42b6-b517-28ad4f11bceb" />

### iv)Image Reflection
<img width="490" height="402" alt="image" src="https://github.com/user-attachments/assets/51b05753-5a54-476f-8d9c-dd72c3b381d2" />

### v)Image Rotation
<img width="506" height="412" alt="image" src="https://github.com/user-attachments/assets/f255f5e8-8275-48b5-bcb3-4a02149bca63" />

### vi)Image Cropping
<img width="527" height="407" alt="image" src="https://github.com/user-attachments/assets/fd242e8a-139e-4900-b350-8c34b3b41b34" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
