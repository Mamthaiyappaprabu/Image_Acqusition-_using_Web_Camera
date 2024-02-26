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
<br>Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
<br>Write the image using imwrite().

### Step 4:
<br>Display the frame using the imshow().

### Step 5:
<br>Divide the frame into halves and assign the smaller frame
### Step 6:
Rotate the frame using the cv2.rotate().

## Program:

#### Developed By: MAMTHA I
#### Register No : 212222230076

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



## ii) Display the video:
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
![Screenshot 2024-02-26 205715](https://github.com/Mamthaiyappaprabu/Image_Acqusition-_using_Web_Camera/assets/119393563/02dbfe7d-1a65-4e34-aa3b-e18ce4f11524)




### ii) Display the video
![image](https://github.com/Mamthaiyappaprabu/Image_Acqusition-_using_Web_Camera/assets/119393563/84bd5c55-b1e8-498d-8bf6-45bfe8941395)




### iii) Display the video by resizing the window
</br>![Screenshot 2024-02-26 204740](https://github.com/Mamthaiyappaprabu/Image_Acqusition-_using_Web_Camera/assets/119393563/f4654b50-30a1-4ea4-85e9-eca32c07549c)

</br>



### iv) Rotate and display the video
</br>![Screenshot 2024-02-26 205019](https://github.com/Mamthaiyappaprabu/Image_Acqusition-_using_Web_Camera/assets/119393563/321058b9-cc1a-4535-b96c-d8679f668406)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
