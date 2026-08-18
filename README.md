# Edge-and-Shape-detection-using-openCV
A Python OpenCV project for detecting edges, contours, and geometric shapes with labels and bounding boxes.

#  Edge and Shape Detection Using OpenCV

##  Project Overview

**Edge and Shape Detection Using OpenCV** is a computer vision project developed using **Python and OpenCV** to detect edges and identify geometric shapes in images.

The project processes an input image, converts it into a suitable format for analysis, detects significant edges using image-processing techniques, and identifies different shapes based on their contours.

This project demonstrates fundamental concepts of **image processing, computer vision, edge detection, contour detection, and shape recognition** using OpenCV.

---

##  Objectives

The main objectives of this project are:

* Detect important edges present in an image.
* Identify contours of objects.
* Detect and classify basic geometric shapes.
* Apply image-processing techniques using OpenCV.
* Understand how computer vision algorithms identify object boundaries.
* Visualize detected edges, contours, and shapes on the input image.

---

##  Project Workflow

The complete workflow of the project is:

```text
                 ┌──────────────────────┐
                 │     Input Image      │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │  Image Preprocessing │
                 │ • Resize Image       │
                 │ • Convert to Gray    │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │   Noise Reduction    │
                 │  Gaussian Blur       │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │    Edge Detection    │
                 │   Canny Algorithm    │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │  Contour Detection   │
                 │   Find Contours      │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │  Shape Detection     │
                 │ • Triangle           │
                 │ • Rectangle          │
                 │ • Square             │
                 │ • Circle             │
                 │ • Other Shapes       │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │  Output Visualization│
                 │ • Edges              │
                 │ • Contours           │
                 │ • Shape Labels       │
                 └──────────────────────┘
```

---

##  How the Project Works

### 1. Input Image

The project takes an image containing different objects or geometric shapes as input.

The image is loaded using OpenCV.

```python
import cv2

image = cv2.imread("input.jpg")
```

---

### 2. Image Preprocessing

The input image is converted from a color image into a **grayscale image**.

Grayscale conversion simplifies the image by reducing the three color channels into a single intensity channel.

```python
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

### 3. Noise Reduction

A Gaussian Blur can be applied to reduce unwanted noise and small variations in the image.

```python
blurred = cv2.GaussianBlur(gray, (5, 5), 0)
```

This helps improve the quality of edge detection.

---

### 4. Edge Detection

The **Canny Edge Detection algorithm** is used to identify boundaries and significant changes in intensity within the image.

```python
edges = cv2.Canny(blurred, 50, 150)
```

The resulting image highlights the edges of objects.

---

### 5. Contour Detection

Contours are detected from the edge or threshold image.

Contours represent the boundaries of objects in an image.

```python
contours, hierarchy = cv2.findContours(
    edges,
    cv2.RETR_EXTERNAL,
    cv2.CHAIN_APPROX_SIMPLE
)
```

---

### 6. Shape Detection

The detected contours are analyzed to determine the approximate shape of each object.

The number of vertices in a contour can help identify basic shapes.

For example:

* **3 vertices → Triangle**
* **4 vertices → Square/Rectangle**
* **More vertices → Circle or other curved shape**

Contour approximation can be performed using:



### 7. Output Visualization

The detected contours and shape names are displayed on the original image.

This makes it possible to visually verify whether the shapes were detected correctly.

---

#  Computer Vision Pipeline

```text
Input Image
     ↓
Grayscale Conversion
     ↓
Gaussian Blur
     ↓
Canny Edge Detection
     ↓
Contour Detection
     ↓
Contour Approximation
     ↓
Shape Classification
     ↓
Draw Contours & Labels
     ↓
Final Output
```

---

## Technologies Used

* **Python**
* **OpenCV**
* **NumPy**
* **Jupyter Notebook / Python IDE**

