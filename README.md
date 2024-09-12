# Record-Image Acquisition using Web Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'
<br>

## Program:

### Developed By:HARINI M D
### Register No:212222230043

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("harini.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()


                            


import cv2
videoCaptureObject = cv2.VideoCapture(0)
frame_count = 0
while(True):
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"frame_{frame_count}.jpg", frame)
    frame_count += 1
    
    if frame_count >= 100:
        break
videoCaptureObject.release()
cv2.destroyAllWindows()       
```




## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('RESULT',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```




## iii) Display the video by resizing the window
```
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
    cv2.imshow('RESULT',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('RESULT',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
![Screenshot 2024-09-12 155736](https://github.com/user-attachments/assets/3c68a817-855b-4cab-b4cb-0189ce7fe6c6)


</br>
</br>


### ii) Display the video
![Screenshot 2024-09-12 160100](https://github.com/user-attachments/assets/9fcd7a35-b9d0-4bb9-a2c7-a26d10e49950)

</br>
</br>


### iii) Display the video by resizing the window

![Screenshot 2024-09-12 160222](https://github.com/user-attachments/assets/03727705-5d44-46eb-8940-51b3aa2b38da)

</br>
</br>



### iv) Rotate and display the video
![Screenshot 2024-09-12 160328](https://github.com/user-attachments/assets/c8c861bf-b0f5-4ace-82b4-29271ed1758c)


</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
