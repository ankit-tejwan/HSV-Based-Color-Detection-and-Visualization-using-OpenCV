# HSV-Based-Color-Detection-and-Visualization
# Color Detection and Visualization in Images

This repository contains code for detecting and visualizing the distribution of colors in an image. The code leverages the OpenCV library to segment colors based on predefined hue ranges and generates a pie chart to visualize the percentage distribution of each detected color.

## Key Features

- Converts an image from BGR to HSV color space for better color segmentation.
- Detects colors using predefined hue ranges (Red, Orange, Yellow, Green, SkyBlue, DarkBlue, Violet, and White).
- Computes the percentage of each color in the image.
- Combines color masks and prevents overlap when counting colors.
- Visualizes the results with:
  - A pie chart showing the percentage distribution of detected colors.
  - Displaying the original image with the detected color areas.

## Requirements

- Python 3.x
- OpenCV
- NumPy
- Matplotlib

You can install the necessary Python libraries using:

```bash
pip install opencv-python numpy matplotlib
```
# Approach
Image Loading and Conversion:


![istockphoto](https://github.com/user-attachments/assets/8e9f1abb-0abc-4b40-81c0-c069d06f84ec)


The input image is loaded using OpenCV (cv2.imread), and it is converted from BGR to HSV color space using cv2.cvtColor. HSV is better for color-based segmentation because it separates color from intensity.

# Color Ranges:

A dictionary (color_ranges) defines hue ranges for various colors such as red, green, blue, etc. These ranges will be used to create color masks that identify the pixels corresponding to each color.

# Mask Creation:

The get_color_mask function generates a binary mask for each color by checking if each pixel in the image falls within the defined hue range. Masks are created using OpenCV's cv2.inRange function.

# Percentage Calculation:

The total number of pixels in the image is calculated.

For each color, the number of matching pixels (non-zero pixels in the mask) is counted using cv2.countNonZero.

The percentage of pixels that belong to each color is calculated by dividing the count of matching pixels by the total number of pixels in the image.

# Color Combination:

A combined mask is created to avoid double-counting overlapping areas by using a bitwise OR operation.

# Visualization:


![distribution_output](https://github.com/user-attachments/assets/1f747711-0672-4ea9-a74d-1a2566560824)


A pie chart is generated to show the color distribution percentages using matplotlib.

The original image is displayed, highlighting the areas of each detected color.

