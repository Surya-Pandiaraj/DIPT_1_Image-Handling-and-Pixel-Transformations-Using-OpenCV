### NAME: SURYA P <br>
### REG NO: 212224230280 <br> 
### Date: 16/10/2026

## EX. No. 1 : Image Handling and Pixel Transformations Using OpenCV

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** SURYA P
- **Register Number:** 212224230280

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
```PYTHON
import cv2
import matplotlib.pyplot as plt
```
## Read the image using OpenCV 
```PYTHON
img = cv2.imread("surya.jpg", cv2.IMREAD_COLOR)
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)#
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
## Display the image using Matplotlib #
```PYTHON
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(708, 708, 3)
```
## Draw a line from top-left to bottom-right
```PYTHON
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(708, 708, 3)
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
(708, 708, 3)
```
## Draw a rectangle around the Whole image
```PYTHON
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
## Add text to the image
```PYTHON
text_img = cv2.putText(img_rgb, "Opencv Drawing", (10, 35), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
## Original RGB Image
```PYTHON
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```
## Convert RGB to HSV
```PYTHON
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```
## Convert RGB to GRAY
```PYTHON
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
## Grayscale Image
```PYTHON
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```
## Convert RGB to YCrCb
```PYTHON
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
## YCrCb Image
```PYTHON
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```
## Convert HSV back to RGB
```PYTHON
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```
## Modify a block of pixels (300x300) to white, starting from (200, 200)
```PYTHON
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
## Display the modified image
```PYTHON
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
image.shape
(708, 708, 3)
```
## Resize the image to half its size
```PYTHON
resized_image = cv2.resize(image, (768 // 2, 600 // 2)) 
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
(300, 384, 3)
```
## Display the resized image
```PYTHON
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
image.shape
(708, 708, 3)
```
## Crop a 300x300 region starting from (50, 50)
```PYTHON
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
## Display the cropped region (ROI)
```PYTHON
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread("surya.jpg") 
```
## Flip the image horizontally (left-right)
```PYTHON
flipped_horizontally = cv2.flip(image, 1)
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
## Horizontal flip
```PYTHON
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```
## Flip the image vertically (up-down)
```PYTHON
flipped_vertically = cv2.flip(image, 0)
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
## Vertical flip
```PYTHON
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(707.5), np.float64(707.5), np.float64(-0.5))
```

## Output:
<br>
<img width="520" height="537" alt="image" src="https://github.com/user-attachments/assets/629716e0-2872-43d5-93f9-f48e91bbe04e" />
<br>
<img width="501" height="532" alt="image" src="https://github.com/user-attachments/assets/5cb55d36-9ee3-47c6-92b9-57c8ca8fe15f" />
<br>
<img width="508" height="532" alt="image" src="https://github.com/user-attachments/assets/5f92ef06-8534-4a82-81a7-ba42c663e479" />
<br>
<img width="538" height="537" alt="image" src="https://github.com/user-attachments/assets/24b3a705-6098-4898-877d-6833677569e8" />
<br>
<img width="508" height="535" alt="image" src="https://github.com/user-attachments/assets/18a4d3b9-75a1-49a9-aeae-09580a839a0d" />
<br>
<img width="527" height="525" alt="image" src="https://github.com/user-attachments/assets/15c8e55f-f3b1-453b-84a5-c0fa2a0e1540" />
<br>
<img width="498" height="517" alt="image" src="https://github.com/user-attachments/assets/9c049564-4b2d-4f8d-b995-59f782d7874e" />
<br>
<img width="508" height="517" alt="image" src="https://github.com/user-attachments/assets/110fe526-ff91-4d93-bccf-d1e18bf5e7c4" />
<br>
<img width="531" height="517" alt="image" src="https://github.com/user-attachments/assets/3ae7eabf-ed30-4d4a-a92d-e774e5162dd1" />
<br>
<img width="528" height="525" alt="image" src="https://github.com/user-attachments/assets/3bad0551-e64c-4548-a3c7-5a3b8631d4f6" />
<br>
<img width="510" height="538" alt="image" src="https://github.com/user-attachments/assets/9e375dd5-219a-4b7d-9436-6a6b6b72911a" />
<br>
<img width="665" height="532" alt="image" src="https://github.com/user-attachments/assets/5ab36c5d-ba91-4cdf-a343-f46270bb2d43" />
<br>
<img width="541" height="531" alt="image" src="https://github.com/user-attachments/assets/d63fd8ac-155f-41dc-999e-550b74beb8c8" />
<br>
<img width="512" height="522" alt="image" src="https://github.com/user-attachments/assets/37864e3c-f207-4748-b6f1-054d438a7ce3" />
<br>
<img width="532" height="523" alt="image" src="https://github.com/user-attachments/assets/a0a184dc-ae25-4119-9291-83751e2c6a21" />
<br>

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
