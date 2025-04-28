
# Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm

### Step 1:
Use cv2.VideoCapture(0) to access web camera.
<br>

### Step 2:
Use cv2.imread to read the video or image.
<br>

### Step 3:
Use cv2.imwrite to save the image.
<br>

### Step 4:
Use cv2.imshow to show the video.
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:

### Developed By:Srivatsan G
### Register No:212223230216

## i) Write the frame as JPG file
```
import cv2
import numpy as np
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("captured_frame.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()

```
## iv) Rotate and display the video

````

cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()

````
## Output

### i) Write the frame as JPG image

![image](https://github.com/user-attachments/assets/58a9af47-1cc0-4dbe-86d4-0240b62050bb)

### ii) Display the video

![image](https://github.com/user-attachments/assets/a3defe78-1681-4ca3-9ae4-ffe4c516857e)


### iii) Display the video by resizing the window

![image](https://github.com/user-attachments/assets/db88f019-13c1-4bae-aa73-ec1c24eedd0f)




### iv) Rotate and display the video

![image](https://github.com/user-attachments/assets/52542705-28c6-4d0e-87fa-2bc273ca26b9)







## Result:
Thus the image is accessed from webcamera and displayed using openCV.
