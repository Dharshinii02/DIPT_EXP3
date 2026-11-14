# Histogram Image Processing

## Experiment Details

- **Name:** Dharshini J
- **Register Number:** 212224240036

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, to write a Python program using OpenCV to perform histogram equalization on a grayscale image.

## Software Required

- Anaconda
- Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

**Step 1:** Read the grayscale and color images using the `cv2.imread()` function.

**Step 2:** Convert the color image into a grayscale image using `cv2.cvtColor()`.

**Step 3:** Display the original grayscale image using `plt.imshow()`.

**Step 4:** Use the `cv2.calcHist()` function to calculate the histogram of the grayscale image and the color image channels.

**Step 5:** Plot the histograms using Matplotlib to represent the frequency of pixel intensities ranging from 0 to 255.

**Step 6:** Perform histogram equalization on the grayscale image using `cv2.equalizeHist()`.

**Step 7:** Calculate and display the histogram of the equalized image.

**Step 8:** Display the original image, equalized image, and their corresponding histograms.

## Program

### i) Histogram of Grayscale Image and Histogram Equalization

```python
# Developed By: Lorena Avelyn R
# Register Number: 212224040174

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the input image
image = cv2.imread("my image.jpg")

# Convert the image to grayscale
gray_image = cv2.cvtColor(
    image, cv2.COLOR_BGR2GRAY
)

# Calculate the original histogram
hist_original = cv2.calcHist(
    [gray_image], [0], None, [256], [0, 256]
)

# Perform histogram equalization
equalized_image = cv2.equalizeHist(gray_image)

# Calculate the equalized histogram
hist_equalized = cv2.calcHist(
    [equalized_image], [0], None, [256], [0, 256]
)

# Display the images and histograms
plt.figure(figsize=(10, 7))

plt.subplot(2, 2, 1)
plt.imshow(gray_image, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

plt.subplot(2, 2, 2)
plt.imshow(equalized_image, cmap="gray")
plt.title("Equalized Image")
plt.axis("off")

plt.subplot(2, 2, 3)
plt.plot(hist_original, color="black")
plt.title("Original Histogram")
plt.xlim([0, 256])

plt.subplot(2, 2, 4)
plt.plot(hist_equalized, color="black")
plt.title("Equalized Histogram")
plt.xlim([0, 256])

plt.tight_layout()
plt.show()
```

## Output

### Input Grayscale Image and Color Image

###  Histogram of Grayscale Image and any channel of Color Image

<img width="537" height="697" alt="image" src="https://github.com/user-attachments/assets/c0c5cf23-fb3a-4471-9748-c77066b2d020" />


###  Histogram Equalization of Grayscale Image

<img width="531" height="687" alt="image" src="https://github.com/user-attachments/assets/b5566cdc-7950-44b2-8a98-920440e8bfaa" />


## Result

Thus, the histogram representing the frequency of pixel intensities ranging from 0 to 255 was obtained for grayscale and color images. Histogram equalization was also successfully performed on the grayscale image using OpenCV.
