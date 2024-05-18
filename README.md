# EX NO-2
# Image_Acqusition-_using_Web_Camera
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
<br>Import the cv2 and numpy package.

### Step 2:
<br>
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
<br>Write the image using imwrite().

### Step 4:
<br>
Display the frame using the imshow().

### Step 5:
<br>Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:

### Developed By:D.Vinitha Naidu
### Register no:212222230175

## i) Write the frame as JPG file
```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```


## ii) Display the video
```

import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    cv2.imwrite("nature.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
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
    cv2.imshow('PIC',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```
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
![WhatsApp Image 2024-05-18 at 12 15 26_04f4865e](https://github.com/VinithaNaidu/Image_Acqusition-_using_Web_Camera/assets/121166004/6d1ae5dd-091f-4d03-a7d2-d2bd3c23d7f7)





### ii) Display the video

![Screenshot 2024-05-18 121959](https://github.com/VinithaNaidu/Image_Acqusition-_using_Web_Camera/assets/121166004/f058a0ad-44fc-41aa-bdfc-6eeedde0ad13)



### iii) Display the video by resizing the window


![Screenshot 2024-05-18 122053](https://github.com/VinithaNaidu/Image_Acqusition-_using_Web_Camera/assets/121166004/9ba514a8-5e15-4acc-b726-79f387f4252d)



### iv) Rotate and display the video
![image](https://github.com/VinithaNaidu/Image_Acqusition-_using_Web_Camera/assets/121166004/e421f4c5-ad54-4e62-8590-343617e1218d)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
