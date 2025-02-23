git add .
git commit -m "sdf"
git push -u origin main


![alt text](images/output.png) 
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

Results and Analysis

Credits

## Technologies Used

Python

OpenCV (cv2)

NumPy

Matplotlib

## How to Install and Run the Project

Clone the repository:

git clone https://github.com/yourusername/coin-detection.git
cd coin-detection

Install the required dependencies:

pip install opencv-python numpy matplotlib

Run the project:

python coin_detection.py

## How to Use the Project

Ensure you have an image named coinn.jpg in the working directory.

Run the script to apply different edge detection methods.

The script will display the results, including edge maps and detected coin contours.

The program will also count and display the number of coins detected.

## Edge Detection Techniques

1. Sobel Edge Detection

Computes gradients in the x and y directions.

Less sensitive to noise and provides smooth edge detection.

2. Prewitt Edge Detection

Similar to Sobel but with simpler kernel operations.

More sensitive to noise but provides sharp contrast edges.

![alt text](<images/output of edge detection using first order derivative prewitt and sobel.png>)

3. mill hilderth edge detection

Uses Laplacian of Gaussian (LoG) to detect zero crossings.

Provides fine, one-pixel-thick edges but may have broken edges.

![alt text](<images/output of using mill hilderth edge detector.png>)

4. Canny Edge Detection

Uses Gaussian filtering and gradient-based thresholding.

Produces clean, connected edges with minimal noise interference.

![alt text](<images/output of canny edge detector.png>)

## Results and Analysis

Sobel Detector: Smooth edges with less noise sensitivity.

Prewitt Detector: Sharp edges but more noise-sensitive.

Marr-Hildreth: Provides thin edges but may have broken edges.

Canny Detector: Most effective, with well-connected edges and minimal noise.

Final Coin Count: The project also counts the total number of coins detected in the image.

![alt text](<images/output of finding no of coins.png>)


