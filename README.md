# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

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
- **Name:** Sasinthara 
- **Register Number:** 212223110045

### Program
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('Qno. 1.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(542, 423, 3)
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(542, 423, 3)
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
(542, 423, 3)
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
image.shape
(542, 423, 3)
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
(300, 384, 3)
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
image.shape
(542, 423, 3)
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(422.5), np.float64(541.5), np.float64(-0.5))

```


## Output:

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/e0388257-def2-4e46-9c8d-3db1802fb115" />

## Image with Line

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/ed028727-41bd-4c8d-9e90-70e812158685" />

## Image with Circle

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/4cebe917-2c12-4c68-b2aa-1ee4d2fd9fe3" />

## Image with Rectangle

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/4dbbff19-f27c-4198-b5ab-1de1b8ecbda5" />

## Image with Text

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/0f7fbae5-dad9-4ab9-81f4-eab3e9482cf1" />



## Original RGB Image

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/27854a1a-006e-4ebf-87e3-de85bf855c10" />

## HSV Image

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/d3d0265b-83cb-4bd0-95a7-2aac66ddac8a" />

## Grayscale Image

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/9c49de18-006c-4a16-afec-d5d0ead9e166" />

## YCrCb Image

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/43507eab-8cbc-4ad7-b4ba-d354d0da71ca" />


## HSV to RGB Image

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/73510aee-1916-4f57-9317-e61c1a07d548" />


## Image with 300x300 White Block


<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/bae82fc9-8aa2-4617-bd28-1b00fbc4fe07" />


## Resized Image (Half Size)

<img width="493" height="410" alt="download" src="https://github.com/user-attachments/assets/b175ad0b-b86e-4a0e-a564-51e40d898733" />


## Cropped Region of Interest (ROI)

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/76b641eb-f1ea-44f5-aae7-d8d9e56976ce" />

## Flipped Horizontally

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/ad97d5b7-538c-4a0f-ae50-3a21a318d77d" />

## Flipped Vertically

<img width="308" height="410" alt="download" src="https://github.com/user-attachments/assets/6b2d9110-bf38-4893-843d-2f7805270260" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

