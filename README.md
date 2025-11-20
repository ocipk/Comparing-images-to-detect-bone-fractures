# Comparing-images-to-detect-bone-fractures

# 📌 Image Comparison Using OpenCV

## 📖 Introduction

This project provides a Python script that uses OpenCV to compare two
images and determine whether they are completely identical. The script
checks image dimensions and color channels, then performs a
pixel-by-pixel subtraction to detect any differences.

## 📚 Table of Contents

-   [Installation](#installation)
-   [Usage](#usage)
-   [Features](#features)
-   [Dependencies](#dependencies)
-   [How-It-Works](#how-it-works)
-   [Example Output](#example-output)
-   [Notes](#notes)

## 🔧 Installation

### 1️⃣ Install Python

Ensure you have **Python 3.7+** installed.

### 2️⃣ Install Required Packages

``` bash
pip install opencv-python
```

## ▶️ Usage

1.  Place your images in the desired directory.

2.  Update the file paths in the script:

    ``` python
    PH1 = cv2.imread(r'path_to_first_image')
    PH2 = cv2.imread(r'path_to_second_image')
    ```

3.  Run the script:

    ``` bash
    python compare_images.py
    ```

## ⭐ Features

-   Compares image size and color channels\
-   Performs pixel-level comparison\
-   Detects whether two images are **exactly identical**

## 📦 Dependencies

-   Python 3.7+
-   OpenCV (cv2)

Install OpenCV:

``` bash
pip install opencv-python
```

## 🔍 How It Works

### 1️⃣ Load the Images

``` python
PH1 = cv2.imread('path_to_image1')
PH2 = cv2.imread('path_to_image2')
```

### 2️⃣ Check if Shapes Match

``` python
if PH1.shape == PH2.shape:
```

### 3️⃣ Subtract the Images

``` python
diff = cv2.subtract(PH1, PH2)
b, g, r = cv2.split(diff)
```

### 4️⃣ Determine Exact Equality

If all channels contain only zero values, the images are identical:

``` python
if cv2.countNonZero(b) == 0 and cv2.countNonZero(g) == 0 and cv2.countNonZero(r) == 0:
    print("The images are completely Equal")
```

## 🧪 Example Output

    The images have the same size and channels
    The images are completely Equal

## ⚠️ Notes

Your original script contained a minor logic issue in the equality
condition.\
You must check that **all** channels have zero non-zero pixels:

``` python
cv2.countNonZero(g) == 0 and cv2.countNonZero(r) == 0
```
