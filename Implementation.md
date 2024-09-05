https://colab.research.google.com/drive/1scc1Bx7n42rj0lacSGJJpT3-Pefjc3Jd?usp=sharing

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Function to display images in a grid
def show_images_grid(images, titles, rows, cols):
    fig, axes = plt.subplots(rows, cols, figsize=(12, 12))
    for i, ax in enumerate(axes.flat):
        if i < len(images):
            ax.imshow(images[i], cmap='gray')
            ax.set_title(titles[i])
            ax.axis('off')
    plt.tight_layout()
    plt.show()

image = cv2.imread('leaf.jpg')

# Step 2: Grayscale Conversion
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Step 3: Apply Gaussian Blur to reduce noise
blurred_image = cv2.GaussianBlur(gray_image, (5, 5), 0)

# Step 4: Edge Detection using Canny Edge Detector
edges = cv2.Canny(blurred_image, 50, 150)

# Step 5: Segmentation (find contours)
contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

# Create a blank image to draw the contours on
segmented_image = np.zeros_like(image)
cv2.drawContours(segmented_image, contours, -1, (0, 255, 0), 2)

# Step 6: Overlay the detected leaf shape on the original image
overlay_image = image.copy()
cv2.drawContours(overlay_image, contours, -1, (0, 255, 0), 2)

# Convert BGR to RGB for displaying in matplotlib
original_image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
segmented_image_rgb = cv2.cvtColor(segmented_image, cv2.COLOR_BGR2RGB)
overlay_image_rgb = cv2.cvtColor(overlay_image, cv2.COLOR_BGR2RGB)

# List of images and titles for the grid
images = [original_image_rgb, gray_image, blurred_image, edges, segmented_image_rgb, overlay_image_rgb]
titles = ['Original Image', 'Grayscale Image', 'Blurred Image', 'Edge Detection', 'Segmented Image', 'Overlay Image']

# Display images in a 3x3 grid (last three slots will be empty)
show_images_grid(images, titles, rows=2, cols=3)
