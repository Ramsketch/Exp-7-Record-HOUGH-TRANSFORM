# Exp-7-Record-HOUGH TRANSFORM

**Name:** RAMKUMAR S

**Register No:** 212225240115

---

## Aim

To implement a basic edge detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**

👉 Write code **ONLY in places marked as `# Your Code Here`**  
👉 Do NOT modify any other part of the code

---

## Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

## Algorithm & Explanation

---

### Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

### Step 2: Read the Image

```python
# Load the image using imread() from cv2 module
image = cv2.imread('board.jpeg')  # Replace 'image.jpg' with your image path
```

---

### Step 3: Convert to Grayscale

```python
# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 4: Edge Detection using Canny Operator

```python
# Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)

# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---

### Step 5: Hough Transform

```python
# Using HoughLinesP(), detect line coordinates for every point in the image
# The parameters are: image, resolution, threshold, minLineLength, maxLineGap

lines = cv2.HoughLinesP(
    edges,
    1,
    np.pi / 180,
    100,
    minLineLength=50,
    maxLineGap=10
)
```

---

### Step 6: Draw the Detected Lines

```python
# Draw the detected lines on the original image

for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```

---


## Expected Output
### Original image

<img width="388" height="394" alt="image" src="https://github.com/user-attachments/assets/e6b8f053-7cc7-4f25-be68-8a4534b81313" />

  
### Grayscale image


<img width="380" height="400" alt="image" src="https://github.com/user-attachments/assets/251c29c6-2470-4062-b3b7-b0e57f7f4782" />

### Canny Edge Detector Output

<img width="390" height="401" alt="image" src="https://github.com/user-attachments/assets/ab2c4106-7b76-49b5-9a0d-83304faa54df" />




### Result of Hough Transform (Detected lines in green color)

<img width="375" height="405" alt="image" src="https://github.com/user-attachments/assets/7bdea39d-897c-46e2-b54b-83f27ad3d909" />



## Result

Thus, the edge detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights edges and lines effectively.

---
