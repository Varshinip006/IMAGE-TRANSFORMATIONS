# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
<br>
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
<br>

Apply various transformations like translation, scaling, shearing, reflection, rotation, and 
cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 

2.Scaling resizes the image by scaling factors. 

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically. 

5.Rotation rotates the image by a given angle.

### Step4:
<br>
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
<br>
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python
Developed By:Priya varshini P
Register Number:212224240119

import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Load the image
image = cv2.imread('c1.jpg')  # Load the image from file
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 

i)Image Translation
# Step 2: Image Translation
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')

ii) Image Scaling
# Step 3: Image Scaling
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')

iii)Image shearing
# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')

iv)Image Reflection
# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')

v)Image Rotation
# Step 6: Image Rotation
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')

vi)Image Cropping
# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')

```
## Output:

<img width="308" height="500" alt="Screenshot 2025-09-03 114902" src="https://github.com/user-attachments/assets/877e96be-b94a-44ce-8863-2759d99da35b" />

### i)Image Translation
<br>
<br>
<br>
<br>
<img width="326" height="505" alt="Screenshot 2025-09-03 114959" src="https://github.com/user-attachments/assets/768de0da-8546-4731-8925-b7576154e1b5" />


### ii) Image Scaling
<br>
<br>
<br>
<br>
<img width="635" height="425" alt="Screenshot 2025-09-03 115028" src="https://github.com/user-attachments/assets/f5d5c898-7d7c-427c-9052-51a4ba6d90ad" />


### iii)Image shearing
<br>
<br>
<br>
<br>
<img width="319" height="502" alt="Screenshot 2025-09-03 115054" src="https://github.com/user-attachments/assets/34b02c10-fd15-4e00-8b15-5623ffcad29f" />


### iv)Image Reflection
<br>
<br>
<br>
<br>
<img width="328" height="511" alt="Screenshot 2025-09-03 115117" src="https://github.com/user-attachments/assets/3ce57c05-813e-49c4-a96c-a2b766a34b51" />

### v)Image Rotation
<br>
<br>
<br>
<br>
<img width="319" height="501" alt="Screenshot 2025-09-03 115153" src="https://github.com/user-attachments/assets/8e75ee93-4995-433a-9ab2-c3e913af7745" />



### vi)Image Cropping
<br>
<br>
<br>
<br>
<img width="620" height="499" alt="Screenshot 2025-09-03 115217" src="https://github.com/user-attachments/assets/31ce734b-1187-4d34-8553-52d6a6378891" />




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
