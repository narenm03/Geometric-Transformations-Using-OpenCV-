# Geometric Transformations Using OpenCV
# NAME: NARENDHARAN M
# REG NO:212223230134
---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
**Name:** AJITH A

### Register No:
212224230012

---

##  Output

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Qn.jpeg') 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off') 
```


<img width="516" height="372" alt="download" src="https://github.com/user-attachments/assets/4fe4b912-19fd-4c69-9641-2f59780edbd2" />

```
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  

translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0])) 
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')
```
<img width="516" height="372" alt="download" src="https://github.com/user-attachments/assets/8814fce3-3dac-449d-adfa-22baec5089db" />

```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```
<img width="516" height="173" alt="download" src="https://github.com/user-attachments/assets/ed1899e7-e2ff-4f65-a5e7-1e0daecdbed4" />

```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```
<img width="516" height="372" alt="download" src="https://github.com/user-attachments/assets/a18b5854-208e-4075-9269-fbbd19e8c02d" />

```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```
<img width="516" height="372" alt="download" src="https://github.com/user-attachments/assets/2939368e-79eb-47bf-b460-d49cf4a880ab" />

```
# Step 6: Image Rotation
(height, width) = image.shape[:2]  
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image")  
plt.axis('off')
```
<img width="516" height="372" alt="download" src="https://github.com/user-attachments/assets/99ec615d-6c95-44f1-a11f-640633be9e71" />

```
# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150  

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
<img width="512" height="410" alt="download" src="https://github.com/user-attachments/assets/c5c049d3-7b5f-4671-b39c-e700011e9c77" />


##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
