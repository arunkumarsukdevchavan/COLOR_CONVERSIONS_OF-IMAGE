# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

## Program:
#### Developed By: ARUN KUMAR SUKDEV CHAVAN
#### Register Number: 212222230013


## Output:

### i) Read and display the image

```python
     import cv2
    image=cv2.imread('photo.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('Arun',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows() 

```


![exp1 1 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/1dc9e30c-f57a-42bc-8f5a-7a00dbbdea3c)

### ii)Write the image

```python
   image=cv2.imread('photo.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
![image](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/7599ed25-96a7-4092-9071-b3061a564cd8)

### iii)Shape of the Image

```python
    image=cv2.imread('photo.jpg',1)
    print(image.shape)
```
![exp1 3](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/77c553e3-564c-4c4d-8973-5a80a217317e)


### iv)Access rows and columns

```python
import random
    image=cv2.imread('photo.jpg',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![exp1 4 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/2dc2f552-8a10-46f6-a5e8-cf7848954243)



### v)Cut and paste portion of image

```python
    image=cv2.imread('photo.jpg',1)
    image=cv2.resize(image,(300,300))
    tag =image[150:200,110:160]
    image[110:160,150:200] = tag
    cv2.imshow('image1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![exp1 5 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/fbb5ec1c-c698-4f25-b80a-c816c0b4c58e)



### vi) BGR and RGB to HSV and GRAY

```python
    img = cv2.imread('photo.jpg',1)
    img = cv2.resize(img,(200,200))
    cv2.imshow('Original Image',img)

    hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
    cv2.imshow('BGR2HSV',hsv1)

    hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
    cv2.imshow('RGB2HSV',hsv2)
    
    gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    cv2.imshow('BGR2GRAY',gray1)
    
    gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
    cv2.imshow('RGB2GRAY',gray2)
    
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![exp1 6 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/13550f72-b8bd-4486-b972-0030a322b369)



### vii) HSV to RGB and BGR

```python
img = cv2.imread('photo.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![exp1 7 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/93b2af60-57b6-47bd-b96e-dd7f3ff6ca61)


### viii) RGB and BGR to YCrCb

```python
img = cv2.imread('photo.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![exp1 8 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/46a08bdb-e58b-4f12-950e-2628d53cf045)

### ix) Split and merge RGB Image
```python
img = cv2.imread('photo.jpg',1)
img = cv2.resize(img,(200,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![exp1 9 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/365d891a-1c25-4b5c-8ea3-5765b886e5c9)

### x) Split and merge HSV Image
```python
img = cv2.imread("photo.jpg",1)
img = cv2.resize(img,(200,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![exp1 10 1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/96ad2fd3-1b39-4a35-837f-8b1d12fbb36a)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
