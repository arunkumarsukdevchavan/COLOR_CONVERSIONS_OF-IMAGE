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
    image=cv2.imread('bird.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('Arun',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/29d419d6-8ce6-4121-aad6-b2a33669d4c7)

![1,1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/b61a4a4c-1115-4453-a357-3b8c53fc0145)


### ii)Write the image

```python
    import cv2
    image=cv2.imread('bird.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
![2](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/904ec4b0-5dbb-484a-bf33-92b917b0128f)

### iii)Shape of the Image

```python
    import cv2
    image=cv2.imread('bird.jpg',1)
    print(image.shape)
```
![3](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/c1935940-6e94-4b50-9918-f1e001a34884)


### iv)Access rows and columns

```python
import random
    import cv2
    image=cv2.imread('bird.jpg',1)
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
![4,1](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/35fd63af-0fe4-40f2-9b2e-29d93f2faf8d)

![4](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/f6ac6cfa-9968-484f-b960-2c1f06d16f0f)


### v)Cut and paste portion of image

```python
  import cv2
  image=cv2.imread('bird.jpg',1)
  image=cv2.resize(image,(300,300))
  tag =image[150:200,110:160]
  image[110:160,150:200] = tag
  cv2.imshow('arun',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()
```
![5](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/85c50e8a-d8bc-4540-ba6b-96895fc26318)


![5,1](https://github.com/arunkumarsukdevchavan/COLOR_CONVERSIONS_OF-IMAGE/assets/118343978/7c5449bb-d4bb-4dd3-8233-bf24a580f221)


### vi) BGR and RGB to HSV and GRAY

```python
import cv2
img = cv2.imread('bird.jpg',1)
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

![6,1](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/3dab3594-1706-4569-97c6-de2f9a27290f)

![6](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/5a970b7f-263b-4ef0-8e8c-186bc7d5d725)


### vii) HSV to RGB and BGR

```python
import cv2
img = cv2.imread('bird.jpg')
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
![7,1](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/db2cc7ef-6d5b-49ca-a18b-65369e55f284)

![7](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/b7fbe4db-3c21-4855-87a2-cbd309cc67ab)


### viii) RGB and BGR to YCrCb

```python
import cv2
img = cv2.imread('bird.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![8](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/2a94ab38-84c3-4b73-8ac7-6c9a6f544603)

![8,1](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/3d295ea6-f6f8-4a40-9855-9d714cf1b0ed)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('bird.jpg',1)
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
![9,1](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/2d600ab5-0304-4181-b2ae-297d488f5bb7)

![9](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/1a047d92-11e0-4c2f-9172-77fde0b60b79)

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("bird.jpg",1)
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
![10](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/530f8e77-6db6-4fc4-a5ea-1e39bef32a1a)

![10,1](https://github.com/Yogeshvar005/COLOR_CONVERSIONS_OF-IMAGE/assets/113497367/d93b352f-7a52-406c-a2a6-47c91616c1ce)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
