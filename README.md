# Ex.No:5 Implementation of filter
# Name: Vignesh.P      
# Register No: 212224230302

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

  
  ```
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  ```
  img = cv2.imread("lion.png")
  img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
  ```
  ```
  plt.imshow(img)
  plt.title("Original Image")
  plt.axis("off")
  plt.show()
  ```
  1. Averaging Filter
  ```
  avg = cv2.blur(img, (5,5))
  plt.imshow(avg)
  plt.title("Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
  2. Weighted Averaging Filter
  ```
  kernel = np.array([[1,2,1],
                   [2,4,2],
                   [1,2,1]], np.float32) / 16
  weighted = cv2.filter2D(img, -1, kernel)
  plt.imshow(weighted)
  plt.title("Weighted Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
3. Gaussian Filter
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()
```
4. Median Filter
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
5. Laplacian Sharpening (Kernel)
```
kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
6. Laplacian Operator
```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

### Smoothing Filters

- Original Image 
<img width="1157" height="596" alt="image" src="https://github.com/user-attachments/assets/e5b109a3-fe9c-4a6b-9f29-8fc3f13edb5f" />


- Weighted averaging provides smoother result with less distortion

 <img width="777" height="437" alt="image" src="https://github.com/user-attachments/assets/5c1e8c26-b78c-4d7d-bedb-cc000182087d" />


 
- Gaussian filter preserves edges better while reducing noise

<img width="818" height="442" alt="image" src="https://github.com/user-attachments/assets/03ce0749-70aa-44c1-a63d-d027c8d4765b" />


- Median filter removes salt-and-pepper noise effectively

<img width="950" height="589" alt="image" src="https://github.com/user-attachments/assets/37808ce4-369d-4dca-973c-5cbd862d7ad3" />



###  Sharpening Filters


<img width="831" height="442" alt="image" src="https://github.com/user-attachments/assets/288fb954-b335-4184-a3a6-d4dff7a0aeb0" />

<img width="766" height="508" alt="image" src="https://github.com/user-attachments/assets/3eaea808-bcd3-4103-b3dd-b9f4bdb0e0ff" />



---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
