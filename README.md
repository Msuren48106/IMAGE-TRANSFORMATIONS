# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Load the image
<br>

### Step2:
Image Translation
<br>

### Step3:
Image Scaling
<br>

### Step4:
Image Shearing
<br>

### Step5:
Image Reflection
<br>

### Step6:
Image Rotation
<br>

### Step7:
Image Cropping
<br>

## Program:
```python
Developed By: M.suren.
Register Number: 212223230222

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Step 1: Load the image
image = cv2.imread('Qno. 1.png')  # Load the image from file



# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 



# Step 2: Image Translation
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  



plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')



# Step 3: Image Scaling
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing




plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')



# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))



plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')



# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes



plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')



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
### i)Image Translation

<br>
<br>
<img width="440" height="516" alt="Screenshot 2026-02-12 104222" src="https://github.com/user-attachments/assets/cae90519-f172-4c93-b10f-7f443e1253af" />

<br>
<br>

### ii) Image Scaling
<br>
<br>
<img width="696" height="367" alt="Screenshot 2026-02-12 104229" src="https://github.com/user-attachments/assets/661c78e8-3141-4d33-bd0a-7bb83d92cfa4" />

<br>
<br>


### iii)Image shearing
<br>
<br>
<img width="454" height="507" alt="Screenshot 2026-02-12 104235" src="https://github.com/user-attachments/assets/c4270551-9497-45bb-9641-97d7cef3216f" />

<br>
<br>


### iv)Image Reflection
<br>
<br>
<img width="473" height="508" alt="Screenshot 2026-02-12 104242" src="https://github.com/user-attachments/assets/cd6d6df8-321b-4a76-b9f0-33841a46c31c" />
<br>
<br>



### v)Image Rotation
<br>
<br>
<img width="420" height="518" alt="Screenshot 2026-02-12 104248" src="https://github.com/user-attachments/assets/acf5da0f-1ca3-4486-9c89-b13516d4e7d9" />

<br>
<br>



### vi)Image Cropping
<br>
<br>
<img width="341" height="507" alt="Screenshot 2026-02-12 104254" src="https://github.com/user-attachments/assets/5f4f2752-76f3-4361-9f5c-d5a59f32b39c" />

<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
