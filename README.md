# EXP-2-Record-Image-Acquisition-using-Web-Camera
## Image Capture and Video Processing Using OpenCV
### Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file

Display the video

Display the video by resizing the window

Rotate and display the video

### 🛠️ Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
### ⚙️ Algorithm
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

### 💻 Program
Developed By:
Name: Divya Dharshini S
Register No: 212224240039
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
### Output
i) Write the frame as JPG image

<img width="855" height="536" alt="Screenshot 2026-11-03 192427" src="https://github.com/user-attachments/assets/5092f37f-73ea-4719-982b-84f71c0a86c8" />


ii) Display the video

<img width="662" height="497" alt="image" src="https://github.com/user-attachments/assets/8b8c176c-cc45-441e-97e5-0c699423945f" />


iii) Display the video by resizing the window

<img width="335" height="490" alt="image" src="https://github.com/user-attachments/assets/c2d8e02a-b084-419f-8f19-8b40564fc9c9" />


iv) Rotate and display the video

<img width="461" height="510" alt="Screenshot 2026-11-03 192406" src="https://github.com/user-attachments/assets/92249f59-153f-4b8f-b4e2-337740e753d3" />


### Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
