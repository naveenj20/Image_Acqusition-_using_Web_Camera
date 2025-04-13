
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
<br> Import the cv2 and numpy package.

### Step 2:
<br> Read the Video frame using the cv2.VideoCapture(0).

### Step 3:
<br> Write the image using imwrite().

### Step 4:
<br> Display the frame using the imshow().

### Step 5:
<br> Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:
``` Python
### Developed By: Naveen Jaisanker
### Register No: 212224110039

## i) Write the frame as JPG file

import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()

## ii) Display the video

import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![Screenshot 2025-04-13 125200](https://github.com/user-attachments/assets/2ec78279-6d21-48ab-b75d-b6da086f36a7)

### ii) Display the video
![Screenshot 2025-04-13 125343](https://github.com/user-attachments/assets/d708600a-2372-4c9e-9fb0-fbcf5f8918c1)

### iii) Display the video by resizing the window
![Screenshot 2025-04-13 125405](https://github.com/user-attachments/assets/3272c3f1-9f7e-48e2-8e4b-8805a9b43119)

### iv) Rotate and display the video
![Screenshot 2025-04-13 125420](https://github.com/user-attachments/assets/e38d05e9-fdb3-411e-aa31-c35ce91c6dab)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
