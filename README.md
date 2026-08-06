## EXPERIMENT - 1-Image-Handling-and-Pixel-Transformations-Using-OpenCV
## AIM:
## Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.

Adjust the brightness of an image.

Modify the image contrast.

Generate a third image using bitwise operations.

## Software Required:
Anaconda - Python 3.7

Jupyter Notebook (for interactive development and execution)

## Algorithm:
## Step 1:

Load an image from your local directory and display it.

## Step 2:

Create a matrix of ones (with data type float64) to adjust brightness.

## Step 3:

Create brighter and darker images by adding and subtracting the matrix from the original image.

Display the original, brighter, and darker images.

## Step 4:

Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).

Display the original, lower contrast, and higher contrast images.

## Step 5:

Split the image (boy.jpg) into B, G, R components and display the channels

Program Developed By:
Name : Harshal Richu S
Reg no: 212225240049
## Step1: Load an image from your local directory and display it.
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('Q1no.jpeg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
## Step2:
o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image.

o Draw a rectangle around a specific region of interest in the image.

o Add the text "OpenCV Drawing" at the top-left corner of the image.

Load the image
```
image = cv2.imread('Q1no.jpeg')
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (878, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
line_img = cv2.line(img_rgb,(678,0),(0,450),(255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
Draw a square at the center of the image.
Load the image
```
image = cv2.imread('Q1no.jpeg')
​

Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(452, 678, 3)
square_img = cv2.rectangle(img_rgb, (520,400), (250,250), (255,0,0), 3)
plt.imshow(square_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
Draw a rectangle around the whole image
Load the image
```
image = cv2.imread('Q1no.jpeg')
​

Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (678, 450), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
​
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
Add the text "OpenCV Drawing" at the top-left corner of the image.

Load the image
```
image = cv2.imread('Q1no.jpeg')
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
Add text to the image
text_img = cv2.putText(img_rgb, "CHEETAH", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
​
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
## Step3:
o Convert the image from RGB to HSV and display it.

o Convert the image from RGB to GRAY and display it.

o Convert the image from RGB to YCrCb and display it.

o Convert the HSV image back to RGB and display it.

Load the image
```
image = cv2.imread('Q1no.jpeg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
## Step4:
o Access and print the value of the pixel at coordinates (100, 100).

o Modify the color of the pixel at (200, 200) to white.
```
Modify a block of pixels (300x300) to white, starting from (200, 200)
image[120:320, 250:400] = [255,255, 255]  # Rows: 200-499, Columns: 200-499
Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

image = cv2.imread("Q1no.jpeg")
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
​
insert_img = cv2.imread("img.jpeg")

Resize while keeping aspect ratio
insert_img = cv2.resize(insert_img, (150, 200))   # Width=150, Height=200
​
insert_img = cv2.cvtColor(insert_img, cv2.COLOR_BGR2RGB)
​

Place it
image_rgb[120:320, 250:400] = insert_img
​
plt.imshow(image_rgb)
plt.title("Image with Inserted Image")
plt.axis("off")
plt.show()
```
## Step5:
o Resize the original image to half its size and display it.

Load the image
```
image = cv2.imread('Q1no.jpeg') 
image.shape
Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
## Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

Load the image
```
image = cv2.imread('Q1no.jpeg') 
image.shape
Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## Step7:
o Flip the original image horizontally and display it.

o Flip the original image vertically and display it.

Load the image
```
image = cv2.imread('Q1no.jpeg') 
Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(677.5), np.float64(451.5), np.float64(-0.5))
Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(677.5), np.float64(451.5), np.float64(-0.5))
```
## Step8:
o Save the final modified image to your local directory.

## OUTPUT
<img width="491" height="275" alt="image" src="https://github.com/user-attachments/assets/0b9dcd92-afb8-4367-a477-f279a8273c0d" />
<img width="487" height="270" alt="image" src="https://github.com/user-attachments/assets/55e617b0-6bab-438b-891e-0ea85c8a5cfe" />
<img width="488" height="281" alt="image" src="https://github.com/user-attachments/assets/45674ccd-62db-45bf-b1e1-107668536533" />
<img width="488" height="268" alt="image" src="https://github.com/user-attachments/assets/b1684786-8a0f-4557-bcfb-74742601c74e" />
<img width="491" height="272" alt="image" src="https://github.com/user-attachments/assets/e7bfbe1f-d0c3-4b67-997a-ab1002fe7b4d" />
<img width="495" height="272" alt="image" src="https://github.com/user-attachments/assets/8a94fedf-6df1-42f6-914a-1f7b54904af2" />
<img width="491" height="267" alt="image" src="https://github.com/user-attachments/assets/e7192e13-8d81-485f-b8b8-c37665962d46" />
<img width="486" height="275" alt="image" src="https://github.com/user-attachments/assets/412869db-fb2f-40ff-b483-6c829d77ed7c" />
<img width="492" height="272" alt="image" src="https://github.com/user-attachments/assets/306db406-b73c-42e9-b57a-85e3c8dc838e" />
<img width="488" height="270" alt="image" src="https://github.com/user-attachments/assets/b9e0ed71-d603-4a4f-8cd4-f776e636c1b9" />
<img width="485" height="270" alt="image" src="https://github.com/user-attachments/assets/4b23d62b-9b7f-46dc-b751-66e4e6398971" />
<img width="461" height="357" alt="image" src="https://github.com/user-attachments/assets/ebd3f1be-c19f-4f11-9b88-5204c19e96ac" />
<img width="358" height="357" alt="image" src="https://github.com/user-attachments/assets/f897b1cc-e2ce-4a07-995c-dbdad6bd923a" />
<img width="487" height="272" alt="image" src="https://github.com/user-attachments/assets/202fbe59-172f-4a24-aadb-306399ce096f" />
<img width="493" height="278" alt="image" src="https://github.com/user-attachments/assets/db53f1f4-720e-4be0-80b1-ce41a1c67331" />
