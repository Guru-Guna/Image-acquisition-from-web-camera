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
<br>
Use VideoCapture(0) to access web camera

### Step 2:
<br>
Use imread to read the video or image

### Step 3:
<br>
Use imwrite to save the image

### Step 4:
<br>
Use imshow to show the video

### Step 5:
<br>
End the program and close the output video windows by pressing 'q'.

## Program:

### Developed By: Gunaseelan G
### Register No: 212221230031

## i) Write the frame as JPG file
```
import cv2
videocaptureobject=cv2.VideoCapture(0)
while True:
    ret,frame=videocaptureobject.read()
    cv2.imwrite("videoimage.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
videocaptureobject.release()
cv2.destroyAllWindows()
```

## ii) Display the video

```
import cv2
videocaptureobject=cv2.VideoCapture(0)
while True:
    ret,frame=videocaptureobject.read()
    cv2.imshow("videoimage.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
videocaptureobject.release()
cv2.destroyAllWindows()

```

## iii) Display the video by resizing the window
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret, frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:,:width//2]=smaller_frame
    image[:height//2,width//2:]=smaller_frame
    image[height//2:,width//2:]=smaller_frame
    
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```


## iv) Rotate and display the video
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret, frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:,:width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2,width//2:]=smaller_frame
    image[height//2:,width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![video image](https://user-images.githubusercontent.com/93427255/226166986-93f49cb1-78d3-4543-b3ca-c66ea0c376b9.png)




### ii) Display the video
</br>
![video image 1](https://user-images.githubusercontent.com/93427255/226166826-66c308bc-ded3-4457-97de-c06037888095.png)

</br>


### iii) Display the video by resizing the window
</br>
![quadrant](https://user-images.githubusercontent.com/93427255/226166873-a0f87ddf-f5af-43a6-a092-4aeead8b3e3d.png)

</br>



### iv) Rotate and display the video
</br>
![rotate](https://user-images.githubusercontent.com/93427255/226166859-93891b8e-02bd-4460-afad-62e11b53ea06.png)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
