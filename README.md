# Real-time Video Analysis for Shape, Circle, and Motion Detection

This is a mini-project for the 21CSE454T Computer Vision course, demonstrating a multi-modal analysis pipeline using OpenCV in Python.

The script processes an input video file to perform three simultaneous detection tasks on each frame:
1.  **Geometric Shape Detection**
2.  **Hough Circle Detection**
3.  **Motion Detection**

## ⚙️ Core Features & Concepts

This project integrates key concepts from the computer vision curriculum into a single application:

* **Shape Detection (Unit 2):**
    * Uses **Canny edge detection** to find object outlines.
    * Applies **`cv2.findContours`** to extract binary shapes.
    * Performs **size filtering** (`cv2.contourArea`) to remove noise.
    * Uses **`cv2.approxPolyDP`** to approximate contours and **label objects** based on their number of vertices (e.g., "Triangle," "Rectangle").

* **Circle Detection (Unit 3):**
    * Employs the **`cv2.HoughCircles`** (Hough Circle Transform) on the grayscale image.
    * This parameter-based method robustly detects circular objects by finding peaks in a 3D accumulator space, making it effective even for noisy or partially occluded circles.

* **Motion Detection (Unit 4 & 5):**
    * Implements **frame differencing** (`cv2.absdiff`) for foreground-background separation.
    * Applies **binary thresholding** to create a motion mask.
    * Uses **morphological opening** (`cv2.morphologyEx`) to clean the mask and remove small, spurious motion noise before drawing bounding boxes.

## 🚀 Technologies Used

* **Python 3**
* **OpenCV (`opencv-python`)**
* **NumPy**

## 🎬 Sample Output

The system processes the video and annotates the frames with its findings.
* **Polygonal shapes** are outlined (e.g., green for triangles, blue for rectangles).
* **Hough Circles** are marked with a red circle.
* **Motion** is captured by a red bounding box.

*(Insert your output screenshots here)*

![Frame 1](frame_1.jpg)
![Frame 2](frame_2.jpg)
![Frame 3](frame_3.jpg)

## 🔧 How to Run

The script is designed to run in a notebook environment like Google Colab or Jupyter.

1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  Install dependencies:
    ```bash
    pip install opencv-python numpy
    ```
3.  Run the script in your environment. It will prompt you to upload a video file.
4.  The script will process 6 frames from the video and display the results.
