# Image-Acquisition-from-Web-Camera
## Aim
 
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
Import cv2 and capture the video using cv2.VideoCapture(0).
<br>

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame).
<br>

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).
<br>

### Step 4:
Display the image until the loop gets over.
<br>

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).
<br>

## Program:
``` Python
### Developed By:Vineesh.M.
### Register No:212221230122.
```
``` Python
## i) Write the frame as JPG file:

import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

```
``` python
## ii) Display the video:

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret,frame = cap.read()
    cv2.imshow('Frame',frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
``` python
## iii) Display the video by resizing the window:
import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
```python
## iv) Rotate and display the video:
import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image:
![screenshot 92](https://user-images.githubusercontent.com/93427254/163662743-baefb20c-46b8-41e7-a175-8945174563fc.jpg)

</br>
</br>


### ii) Display the video:
![Screenshot (91)](https://user-images.githubusercontent.com/93427254/163662942-40d051cd-c5ae-4e3d-bd3e-f624aadf057c.png)


</br>
</br>


### iii) Display the video by resizing the window:
![Screenshot (90)](https://user-images.githubusercontent.com/93427254/163662761-c9fd04b7-018e-43ad-b8eb-9c1e7e151318.png)

</br>
</br>



### iv) Rotate and display the video:
![Screenshot (89)](https://user-images.githubusercontent.com/93427254/163662954-5eba7d7b-f055-4a99-964a-9b81a9e69e10.png)


</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
