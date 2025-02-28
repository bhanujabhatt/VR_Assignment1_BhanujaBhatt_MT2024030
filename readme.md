git add .
git commit -m "sdf"
git push -u origin main


# 1)Coin Detection and Segmentation

## Project Description

This project aims to detect, segment, and count coins in an image using various edge detection and segmentation techniques. The methods implemented include first-order derivative edge detectors (Sobel and Prewitt), the Marr-Hildreth edge detector, and the Canny edge detector. Additionally, region-based segmentation techniques are applied to isolate individual coins from the image. The effectiveness of each technique is analyzed in terms of noise sensitivity, edge continuity, segmentation accuracy, and counting precision.

## Table of Contents

1  Technologies Used <br>
2  How to Install and Run the Project
3  How to Use the Project
4  Edge Detection Techniques
5  Sobel Edge Detection
6  Prewitt Edge Detection
7  Marr-Hildreth Edge Detection
8  Canny Edge Detection
9  Coin Segmentation
10 count of total no detected coins
11 Results and Analysis
12 Future Scope

## Technologies Used

. Python(Python 3.9.21)
. OpenCV (cv2 4.11.0)
. NumPy
. Matplotlib

## How to Install and Run the Project

.Clone the repository:
.git clone https://github.com/bhanujabhatt/VR_Assignment1_BhanujaBhatt_MT2024030.git
cd VR_Assignment1_BhanujaBhatt_MT2024030

Install the required dependencies:
pip install opencv-python numpy matplotlib

Run the project


## How to Use the Project

Ensure you have an image named coin.jpeg in the working directory.
Run the script to apply different edge detection methods.
The script will display the results, including edge maps, detected coin contours, and segmented outputs.
The program will also count and display the number of coins detected.

## Edge Detection Techniques

### 1. Sobel Edge Detection
Computes gradients in the x and y directions.
Less sensitive to noise and provides smooth edge detection.

### 2. Prewitt Edge Detection
Similar to Sobel but with simpler kernel operations.
More sensitive to noise but provides sharp contrast edges.
![alt text](<output images/output using first order derivatiove sobel and prewitt.png>)

#### conclusion 

Sobel is less sensitive to noise__
Prewitt is more sensitive to noise__
Sobel generally performs better when you want more accurate, less noisy edges, especially in the presence of noise.__
Prewitt is generally used when you want simpler, faster computations and you are dealing with less noisy images__
Sobel X/Y might produce less extreme values or smoother gradients, which are more subtle, leading to gradual gray-scale variations.__
Prewitt X/Y, by contrast, might produce a stronger contrast in its edge detections, where you have stark differences between edge and non-edge pixels, hence appearing as black and white.

### 3. Mill hilderth edge detection
Uses Laplacian of Gaussian (LoG) to detect zero crossings.
Provides fine, one-pixel-thick edges but may have broken edges.
![alt text](<output images/USING Marr-Hildreth EDGE DETECTOR.png>)

#### conclusion

broken edges are present__
one pixel thick edges__
less error(get true edges)__

### 4. Canny Edge Detection
Uses Gaussian filtering and gradient-based thresholding.
Produces clean, connected edges with minimal noise interference.
![alt text](<output images/USING CANNY EDGE DETECTOR.png>)


#### conclusion

less broken edges
one pixel thick edges
less error(get true edges)

## Coin Segmentation

### Region Splitting & Merging

Steps:

Convert the image to grayscale.
Apply Gaussian Blur to reduce noise.
Apply Otsu’s Thresholding to create a binary image.
Region Splitting:
Recursively divide the image into smaller regions based on intensity variance.
Stop splitting if variance is low or the region size is too small.
Region Merging:
Merge regions based on similarity (average intensity difference).
Assign detected coin regions as the foreground.
Extract individual coins using Connected Components Analysis.
Display the segmented coins and extracted individual coins.

Pros & Cons:

✅ Avoids over-segmentation by only splitting where necessary.
✅ Works well for well-separated coins.
❌ May not perform well if coins are touching or overlapping.
![alt text](<output images/using region splitting and merging 1.png>)
![alt text](<output images/region splitting and merging2.png>)
![alt text](<output images/region splitting and merging 3.png>)

2. Watershed Algorithm

Steps:
Convert the image to grayscale.
Apply Gaussian Blur and Otsu’s Thresholding.
Perform Morphological Closing to enhance object connectivity.
Compute Distance Transform and extract the sure foreground.
Define the sure background using dilation.
Identify the unknown region (difference between foreground and background).
Label different regions using Connected Components Analysis.
Apply the Watershed Algorithm, marking boundaries where needed.
Extract individual coins by isolating segmented components.
Display the segmented image and extracted coins.

Pros & Cons:

✅ Effectively segments touching and overlapping coins.
✅ Works well for objects with clear boundaries.
❌ May detect unnecessary boundaries in noisy images.
![alt text](<output images/watershed1.png>)
![alt text](<output images/watershed2.png>)

## Total count of coin detected

 The script applies grayscale conversion, Gaussian blurring, adaptive thresholding, and morphological processing to identify circular objects (coins). It filters contours based on area and circularity to ensure accurate counting. The detected coins are outlined in green, and the total count is displayed.
1. Load the Image
Read the image using cv2.imread() and store it for further processing.

2. Convert to Grayscale
Convert the image to grayscale using cv2.cvtColor() to simplify processing.

3. Apply Gaussian Blur
Use cv2.GaussianBlur() to smooth the image and reduce noise.

4. Apply Adaptive Thresholding
Use cv2.adaptiveThreshold() to create a binary image, highlighting coin edges.

5. Use Morphological Operations
Apply cv2.morphologyEx() to close small gaps and remove noise.

6. Find Contours
Use cv2.findContours() to detect object boundaries in the processed image.

7. Filter Circular Contours
Compute perimeter, area, and circularity to identify coin-like objects.
Use a circularity threshold (0.7 - 1.2) to filter only round objects.

8. Count and Draw Detected Coins
Increment the coin count for each valid circular contour.
Use cv2.drawContours() to outline detected coins in green.

9. Convert Image to RGB
Convert from BGR to RGB for correct color representation in Matplotlib.

10. Display the Result
 Use matplotlib.pyplot to show the processed image with the coin count.

11. Print the Total Number of Coins
Output the total count of detected coins in the console.
![alt text](<output images/count no of coins.png>)


## Results and Analysis
Edge Detection Techniques
Sobel Edge Detection

Strengths: Highlights edges well and is computationally efficient.
Weaknesses: Sensitive to noise and not ideal for segmentation.
Prewitt Edge Detection

Strengths: Simple computation, good for basic edge detection.
Weaknesses: More noise-sensitive than Sobel.
Marr-Hildreth Edge Detection

Strengths: Captures finer edges and is useful for high-contrast images.
Weaknesses: Can produce broken edges.
Canny Edge Detection

Strengths: Best noise suppression, provides clear and connected edges.
Weaknesses: Computationally expensive.
Segmentation Techniques
Region Splitting & Merging

Strengths: Avoids over-segmentation and works well for well-separated objects.
Weaknesses: Fails with overlapping or touching coins.
Watershed Algorithm

Strengths: Effectively segments touching and overlapping coins.
Weaknesses: May detect extra boundaries in noisy images.

## Future Scope
Implement deep learning-based detection (e.g., using CNNs)
Improve robustness for complex backgrounds
Develop a real-time detection system using OpenCV and a webcam



# 2) Image Stitching 

## Project Description

This project demonstrates image stitching by combining multiple images into a single panoramic image. The implementation is done using OpenCV and employs two different approaches:

Feature-based Image Stitching: Uses SIFT (Scale-Invariant Feature Transform) for keypoint detection, BFMatcher for feature matching, and homography estimation for warping and stitching.

Automated Stitching using OpenCV's Stitcher_create(): A simpler alternative that leverages OpenCV's built-in stitching module.

## Technologies Used

OpenCV: For image processing and feature extraction.

NumPy: For numerical operations and matrix manipulations.

Matplotlib: For visualization and debugging.

ImageIO: For reading and writing images.

Imutils: For image transformations and resizing.

## How to Install and Run the Project

Clone the repository:

git clone https://github.com/bhanujabhatt/VR_Assignment1_BhanujaBhatt_MT2024030.git

cd VR_Assignment1_BhanujaBhatt_MT2024030

Install the required dependencies:

pip install opencv-python numpy matplotlib imageio imutils

Run the project

## Input

Two or more overlapping images that need to be stitched together.

## Output

A single stitched panoramic image.

## Implementation Details

### using keypoint

1)Feature Extraction: SIFT extracts keypoints and descriptors.

![alt text](<output images/keypint.png>)

2)Feature Matching: BFMatcher with KNN finds corresponding points.

![matching](<output images/matching.png>)

![matching using knn](<output images/matching using knn.png>)

### conclusion

1)BFMatcher is going to try all the possibilities (which is the meaning of "Brute Force" and hence it will find the best matches.
2)FLANN, meaning "Fast Library for Approximate Nearest Neighbors", will be much faster but will find an approximate nearest neighbors. 
WE ARE USING bf because there are only 2 images we are planning to stich
3)BFMatcher.match()
Finds the best match for each descriptor in the query set.
4)BFMatcher.knnMatch()
Finds the k best matches for each descriptor.
5)KNN provides a larger set of candidate features.


3)Filtering Matches: Lowe’s ratio test retains only good matches.

4)Homography Calculation: Determines the transformation matrix.

[[ 5.82900750e-01  3.23978100e-02  4.33868600e+02]
 [-1.64669865e-01  8.28759249e-01  1.16199037e+02]
 [-2.61629253e-04 -1.42613971e-05  1.00000000e+00]]

Warping and Stitching: Aligns and blends the images.

![without warping](<output images/pre output using keypoint.png>)

![final output](<output images/output using keypoint.png>)
 
 ### USING CV2 Stitcher_create()

Image Loading: Reads images and converts them to RGB for proper visualization.

Stitching Process:

Uses OpenCV’s Stitcher_create() to perform automatic image stitching.

If successful, saves and displays the stitched output.

![alt text](<output images/pre output using cv2 stiching.png>)

Post-Processing:

Applies a border to the stitched image to prevent cropping artifacts.
![alt text](<output images/mask using cv2 pre stching.png>)

Converts the stitched image to grayscale and applies thresholding.

Detects external contours and refines the mask using erosion.
![alt text](<output images/finalmask using cv2.png>)

Extracts the bounding rectangle and crops the final output.

Final Output: Saves the refined image and displays it using Matplotlib.
![alt text](<output images/stiched image using cv2.png>)
