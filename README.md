# EXPERIMENT 05: IMAGE TRANSFORMATION
## AIM:
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the required libraries.
### Step 2:
Read the image and convert the image from RGB to BGR.
### Step 3:
Perform image translation on the image.
### Step 4:
Perform image scaling on the image.
### Step 5:
Perform image shearing on the image.
### Step 6:
Perfrom image reflection on the image.
### Step 7:
Perfrom image rotation on the image.
### Step 8:
Perfrom image cropping on the image.

## PROGRAM:
```
Developed By: RITHIGA SRI.B
Register Number: 212221230083
```
1.Image Translation
```
#Read the input image
img=cv2.imread("pic.jpg")

#Convert from BGR to RGB so we can plot using matplotlib
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

#Disable x & y axis
plt.axis("off")

#Show the image
plt.imshow(img)
plt.show()

#Get the image shape
rows,cols,dim=img.shape

#Transformation matrix for translation
M=np.float32([[1,0,100],
             [0,1,50],
             [0,0,1]])

#Apply a perspective transformation to the image
translated_img=cv2.warpPerspective(img,M,(cols,rows))

#Disable x & y axis
plt.axis("off")

#Show the resultig image
plt.imshow(translated_img)
plt.show()
```

2.Image Scaling
```
#Disable x & y axis
plt.axis("off")

#Show the original image
plt.imshow(img)
plt.show()

#Transformation matrix for scaling
M=np.float32([[1.5,0,0],
              [0,1.8,0],
              [0,0,1]])

#Apply a perspective transformation to the image
scaled_img=cv2.warpPerspective(img,M,(cols*2,rows*2))


#Disable x & y axis
plt.axis("off")

#Show the resultig image
plt.imshow(scaled_img)
plt.show()
```
3.Image shearing
```
#Transformation matrix for Shearing
#Shearing applied to x-axis
M_x=np.float32([[1,0.8,0],
               [0,1,0],
               [0,0,1]])

#Shearing applied to y-axis
M_y=np.float32([[1,0,0],
               [0.3,1,0],
               [0,0,1]])

#Apply a perspective transformation to the image
sheared_img_xaxis=cv2.warpPerspective(img,M_x,(int(cols*1.5),int(rows*1.5)))
sheared_img_yaxis=cv2.warpPerspective(img,M_y,(int(cols*1.5),int(rows*1.5)))

#Disable x & y axis
plt.axis("off")

#Show the resulting image
plt.imshow(sheared_img_xaxis)
plt.show()

#Disable x & y axis
plt.axis("off")

#Show the resulting image
plt.imshow(sheared_img_yaxis)
plt.show()
```
4.Image Reflection
```
#Transformation matrix for x-axis reflection
M_x=np.float32([[1,0,0],
               [0,-1,rows],
               [0,0,1]])

#Trasformation matrix for y-axis reflection
M_y=np.float32([[-1,0,cols],
             [0,1,0],
             [0,0,1]])

#Apply a perspective transformation to the image
reflected_img_xaxis=cv2.warpPerspective(img,M_x,(int(cols),int(rows)))
reflected_img_yaxis=cv2.warpPerspective(img,M_y,(int(cols),int(rows)))

#Disable x & y axis
plt.axis("off")

#Show the resulting image
plt.imshow(reflected_img_xaxis)
plt.show()

#Disable x & y axis
plt.axis("off")

#Show the resulting image
plt.imshow(reflected_img_yaxis)
plt.show()
```
5.Image Rotation
```
#Angle from degree to radian
angle=np.radians(30)

#Transformation matrix for Rotation
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
             [np.sin(angle),np.cos(angle),0],
             [0,0,1]])

#Apply a perspective transformation to the image
rotated_img=cv2.warpPerspective(img,M,(int(cols),int(rows)))

#Disable x & y axis
plt.axis("off")

#Show the resulting image
plt.imshow(rotated_img)
plt.show()
```
6.Image Cropping
```
#Get 200 pixels from 100 to 300 on both x axis and y axis
cropped_img=img[100:300,100:300]

#Disable x & y axis
plt.axis("off")

#Show the resulting image
plt.imshow(cropped_img)
plt.show()
```

## OUTPUT:
### (i)Image Translation:
![image](https://user-images.githubusercontent.com/93427256/230755430-505e7dec-abfe-4903-897b-f858394cd0ec.png)

### (ii) Image Scaling:
![image](https://user-images.githubusercontent.com/93427256/230755451-3b8e7aff-ebd5-458f-a024-9265542e859a.png)

### (iii)Image shearing:
![image](https://user-images.githubusercontent.com/93427256/230755463-987960e9-eb9b-4b6a-85af-70ba61d2dab8.png)

### (iv)Image Reflection:
![image](https://user-images.githubusercontent.com/93427256/230755476-bb385b30-61b3-4820-aa49-98d4f2de47ff.png)

### (v)Image Rotation:
![image](https://user-images.githubusercontent.com/93427256/230755481-b6d4335c-da6c-4021-b4b0-cf85d8539f08.png)

### (vi)Image Cropping:
![image](https://user-images.githubusercontent.com/93427256/230755493-4e231791-e79e-47fe-8ead-26a4132810af.png)

## RESULT: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
