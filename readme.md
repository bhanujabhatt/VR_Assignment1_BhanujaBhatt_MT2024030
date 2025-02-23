git add .
git commit -m "sdf"
git push -u origin main


# Coin Detection and Counting using Edge Detection Techniques

## Project Description

This project focuses on detecting and counting coins in an image using various edge detection techniques. The methods implemented include first-order derivative edge detectors (Sobel and Prewitt), the Marr-Hildreth edge detector, and the Canny edge detector. Each technique's effectiveness is analyzed in terms of noise sensitivity, edge continuity, and accuracy in detecting the true edges of the coins.

## Table of Contents

Technologies Used

How to Install and Run the Project

How to Use the Project

Edge Detection Techniques

Sobel Edge Detection

Prewitt Edge Detection

Marr-Hildreth Edge Detection

Canny Edge Detection

count of total no detected coins

Results and Analysis

## Technologies Used

Python(Python 3.9.21)

OpenCV (cv2 4.11.0)

NumPy

Matplotlib

## How to Install and Run the Project

Clone the repository:

git clone https://github.com/bhanujabhatt/VR_Assignment1_BhanujaBhatt_MT2024030.git

cd VR_Assignment1_BhanujaBhatt_MT2024030

Install the required dependencies:

pip install opencv-python numpy matplotlib

Run the project


## How to Use the Project

Ensure you have an image named coinn.jpg in the working directory.

Run the script to apply different edge detection methods.

The script will display the results, including edge maps and detected coin contours.

The program will also count and display the number of coins detected.

## Edge Detection Techniques

### 1. Sobel Edge Detection

Computes gradients in the x and y directions.

Less sensitive to noise and provides smooth edge detection.

### 2. Prewitt Edge Detection

Similar to Sobel but with simpler kernel operations.

More sensitive to noise but provides sharp contrast edges.

![alt text](<images/output of edge detection using first order derivative prewitt and sobel.png>)

#### conclusion 

Sobel is less sensitive to noise
Prewitt is more sensitive to noise
Sobel generally performs better when you want more accurate, less noisy edges, especially in the presence of noise.
Prewitt is generally used when you want simpler, faster computations and you are dealing with less noisy images
Sobel X/Y might produce less extreme values or smoother gradients, which are more subtle, leading to gradual gray-scale variations.
Prewitt X/Y, by contrast, might produce a stronger contrast in its edge detections, where you have stark differences between edge and non-edge pixels, hence appearing as black and white.

### 3. mill hilderth edge detection

Uses Laplacian of Gaussian (LoG) to detect zero crossings.

Provides fine, one-pixel-thick edges but may have broken edges.

![alt text](<images/output of using mill hilderth edge detector.png>)

#### conclusion

broken edges are present
one pixel thick edges
less error(get true edges)

### 4. Canny Edge Detection

Uses Gaussian filtering and gradient-based thresholding.

Produces clean, connected edges with minimal noise interference.

![alt text](<images/output of canny edge detector.png>)

#### conclusion

less broken edges
one pixel thick edges
less error(get true edges)

## total count of coin detected
Load the Image

    The script reads the image file (coinn.jpg).

Resize for Consistency

    The image is resized to 80% of its original size while maintaining the aspect ratio.

Convert to Grayscale

    The image is converted to a grayscale format to simplify processing.

Apply Adaptive Thresholding

    Adaptive Gaussian thresholding is used to highlight the coins against the background.

Find Contours

    Contours (edges of objects) are detected in the thresholded image.

Filter Contours by Area

    Small contours (noise) are removed based on a minimum area threshold (5000 pixels).

Draw Contours and Count Coins

    The detected coin contours are drawn in green, and the number of coins is counted.

Display Results

    The processed image with detected coins is displayed along with the total count.

   ![alt text](<images/output of finding no of coins.png>)
    
## Results and Analysis

Sobel Detector: Smooth edges with less noise sensitivity.

Prewitt Detector: Sharp edges but more noise-sensitive.

Marr-Hildreth: Provides thin edges but may have broken edges.

Canny Detector: Most effective, with well-connected edges and minimal noise.

Final Coin Count: The project also counts the total number of coins detected in the image.



