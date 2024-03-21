# Implementation-of-filter

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step3:
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

### Step4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step5:
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.

### Step 6:
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:

### Developed By: SWETHA S
### Register Number: 212222230155

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```

ii) Using Weighted Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title('WEIGHTED AVERAGE FILTERING')
```

iii) Using Gaussian Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

guassian_blur=cv2.GaussianBlur(src=image2,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.imshow(guassian_blur)
plt.title('GAUSSIAN FILTER')
```

iv) Using Median Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

median=cv2.medianBlur(src=image2,ksize=11)
plt.imshow(median)
plt.title('MEDIAN FILTER')
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
image3=cv2.filter2D(image2,-1,kernel3)

plt.imshow(image3)
plt.title('LAPLACIAN KERNEL')
```

ii) Using Laplacian Operator
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("anne.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

new_image=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(new_image)
plt.title('LAPLACIAN OPERATOR')
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![Screenshot 2024-03-22 000500](https://github.com/swethaselvarajm/Implementation-of-filter/assets/119525603/fa7fe24e-b779-447d-87a8-0c6d0433cb4e)

ii) Using Weighted Averaging Filter

![Screenshot 2024-03-22 000554](https://github.com/swethaselvarajm/Implementation-of-filter/assets/119525603/e4e81421-f108-4fe9-91ef-de811c6e93cc)


iii) Using Gaussian Filter

![Screenshot 2024-03-22 000644](https://github.com/swethaselvarajm/Implementation-of-filter/assets/119525603/26a95d31-d826-445b-88ac-6121975076de)

iv) Using Median Filter

![Screenshot 2024-03-22 000735](https://github.com/swethaselvarajm/Implementation-of-filter/assets/119525603/98588fa7-6a32-4d8d-8e25-1590c3573e2c)

### 2. Sharpening Filters

i) Using Laplacian Kernal

![Screenshot 2024-03-22 000812](https://github.com/swethaselvarajm/Implementation-of-filter/assets/119525603/2208c21c-785e-40e1-922a-330256e3c0ab)

ii) Using Laplacian Operator

![Screenshot 2024-03-22 000900](https://github.com/swethaselvarajm/Implementation-of-filter/assets/119525603/3a0ae49a-082f-439b-a936-fd6547fc840f)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
