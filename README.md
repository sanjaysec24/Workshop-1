# DIPT-WORKSHOP-1
## Adding Sunglasses to Your Passport Photo Using OpenCV
## Name : SanjayKumar B
## Reg.no : 21224230242
```
# Import libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the Face Image
faceImage = cv2.imread("photo .png")
plt.imshow(cv2.cvtColor(faceImage, cv2.COLOR_BGR2RGB))
plt.title("Face")
plt.axis("off")
# Load the Sunglass image with Alpha channel
glassPNG = cv2.imread("sunglass.jpeg", cv2.IMREAD_UNCHANGED)
plt.imshow(cv2.cvtColor(glassPNG, cv2.COLOR_BGRA2RGBA))
plt.title("glassPNG")
plt.axis("off")
# Resize the sunglass to fit the face
# Tuned for the uploaded image
glassPNG = cv2.resize(glassPNG, (170, 63), interpolation=cv2.INTER_AREA)
print(glassPNG.shape)
# Separate the Color and alpha channels
glassBGR = glassPNG[:,:,0:3]
glassMask1 = glassPNG[:,:,2]
glassBGR.shape
# Display the images for clarity
plt.figure(figsize=[15,15])
plt.subplot(121);plt.imshow(glassBGR[:,:,::-1]);plt.title('Sunglass Color channels');
plt.subplot(122);plt.imshow(glassMask1,cmap='gray');plt.title('Sunglass Alpha channel');
# Make a copy
#faceWithGlassesNaive = resized_faceImage.copy()
faceWithGlassesNaive = faceImage.copy()

# Replace the eye region with the sunglass image
faceWithGlassesNaive[750:1000,480:1250]=glassBGR

plt.imshow(faceWithGlassesNaive[...,::-1])
glassBGR.shape
```

<img width="308" height="409" alt="download" src="https://github.com/user-attachments/assets/3ffd6495-5963-47e3-9919-36dcafaba632" />

<img width="515" height="271" alt="download" src="https://github.com/user-attachments/assets/f16f0415-582e-48a9-b6dd-a431e314b4af" />

<img width="1209" height="259" alt="download" src="https://github.com/user-attachments/assets/ffd5c590-b75c-4bfd-a64f-08d03f068ed9" />

<img width="620" height="790" alt="download" src="https://github.com/user-attachments/assets/e0e01dd2-fbf6-42d4-828b-829127d9e78b" />

<img width="1176" height="656" alt="download" src="https://github.com/user-attachments/assets/28bb2e23-52ed-44f2-b883-43349c077e18" />
