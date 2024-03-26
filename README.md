# Computer Vision Masterclass - Face and Eye Detection

This repository contains Python code that demonstrates how to use OpenCV for face and eye detection in images. The code is based on the Computer Vision Masterclass and provides examples of loading images, detecting faces and eyes, and drawing rectangles around the detected regions.

## Prerequisites

Before running the code, you need to have the following dependencies installed:

- Python 3.x
- OpenCV (cv2)

You can install OpenCV using pip:
## Usage

1. Clone the repository or download the code files.
2. Make sure you have the necessary image files and XML cascade files in the correct locations specified in the code.
3. Run the Python scripts in your preferred Python environment or IDE.

## Code Explanation

### Face Detection

The code demonstrates how to load an image, convert it to grayscale, and use OpenCV's built-in Haar Cascade Classifier to detect faces in the image. It then draws rectangles around the detected faces.

```python
import cv2

# Load the image
image = cv2.imread('/path/to/your/image.jpg')

# Convert the image to grayscale
image_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Load the face detector
face_detector = cv2.CascadeClassifier('/path/to/haarcascade_frontalface_default.xml')

# Detect faces in the grayscale image
detections = face_detector.detectMultiScale(image_gray)

# Draw rectangles around the detected faces
for (x, y, w, h) in detections:
    cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)

# Display the image with detected faces
cv2.imshow('Face Detection', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
