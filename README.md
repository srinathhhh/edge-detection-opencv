# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

- **Name:** SRINATH N
- **Register No:** 2305003009
  
## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('wolf.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
```python

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
```python
image = cv2.imread("wolf.jpg")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(canny_edges, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')
```
```python
roberts_x = np.array([[1, 0],
                      [0, -1]])

roberts_y = np.array([[0, 1],
                      [-1, 0]])

roberts_x_edge = cv2.filter2D(gray, -1, roberts_x)
roberts_y_edge = cv2.filter2D(gray, -1, roberts_y)
roberts = cv2.magnitude(roberts_x_edge.astype(np.float32),
                        roberts_y_edge.astype(np.float32))
plt.imshow(canny_edges, cmap='gray')
plt.title('Roberts Edge Detection')
plt.axis('off')  

```


---

## Output
### Orginal Image

<img width="515" height="392" alt="download" src="https://github.com/user-attachments/assets/d50131b1-b955-46bb-abe7-125d2155d8d7" />


###  Sobel Edge Detector

<img width="515" height="392" alt="download" src="https://github.com/user-attachments/assets/a9f72a6e-a9cd-4046-8754-3a734092bc0b" />


###  Prewitt Edge Detector


<img width="515" height="392" alt="download" src="https://github.com/user-attachments/assets/881417e8-1e84-4389-8d67-78975c8c1840" />


###  Roberts Edge Detector


<img width="515" height="392" alt="download" src="https://github.com/user-attachments/assets/b647bbf5-b9ac-44e1-936e-20950a440223" />



###  Laplacian Edge Detector


<img width="515" height="392" alt="download" src="https://github.com/user-attachments/assets/95ec1ffa-a19f-4387-a489-b1b9660f0f60" />



###  Canny Edge Detector

<img width="515" height="392" alt="download" src="https://github.com/user-attachments/assets/728ff588-5b58-488a-b459-cca1bd7993ec" />


---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
