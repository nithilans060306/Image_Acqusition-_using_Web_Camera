
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import CV2,numpy and the other required libraries

### Step 2:
Create an instance of Video Capture and save the displayed image

### Step 3:
Capture video and using numpy resize the shape of the window and display the video

### Step 4:
Rotate the captured image by 180*

## Program:
```Python
# Developed By: Nithilan S
# Register No: 212223240108

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
## Output

### i) Write the frame as JPG image
<img width="643" height="507" alt="image" src="https://github.com/user-attachments/assets/dd035041-8688-4b4a-b8f4-57cc1dbe5ff6" />

### ii) Display the video
<img width="638" height="483" alt="image" src="https://github.com/user-attachments/assets/80ee7c67-930b-4bdd-957e-cfdbfbd9db32" />

### iii) Display the video by resizing the window
<img width="331" height="484" alt="image" src="https://github.com/user-attachments/assets/affcd91e-6924-4332-9818-d9f58c768037" />

### iv) Rotate and display the video
<img width="368" height="484" alt="image" src="https://github.com/user-attachments/assets/dfe122be-d44f-436c-a316-34b6ee70521e" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
