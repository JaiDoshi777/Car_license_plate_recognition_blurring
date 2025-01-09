# Car_number_plate_recognition_blurring
Utilized computer vision to recognize and blur the number plate of a car

This can be useful for privacy reasons, such as when the car owner does not wish to share their license plate number in a photo.

The script begins with importing essential libraries, including cv2 for OpenCV functionalities, matplotlib.pyplot for image display, and numpy for numerical operations. The car image is then read using OpenCV's imread function and displayed using a helper function named display, which utilizes Matplotlib for visualization.

To detect the number plate, the code loads a pre-trained Haar Cascade classifier for Russian license plates using cv2.CascadeClassifier. Haar Cascades are effective for object detection due to their ability to identify features based on intensity differences in the image.

A function named detect_license_plate is defined to detect and mark the license plate in the image. The image is copied to avoid modifying the original, and the detectMultiScale method of the Haar Cascade classifier is used to detect the license plate. The method returns a list of bounding boxes, each represented by the coordinates (x, y, w, h) indicating the position and size of the detected plate. For each detected plate, a rectangle is drawn around it using cv2.rectangle, and the modified image with the detected license plate is returned and displayed.

The next part of the code involves blurring the detected license plate. A function named blur_plate is defined for this purpose. The function works similarly to the detection function, but instead of drawing a rectangle, it applies a median blur to the region of interest (ROI) containing the license plate. The detectMultiScale method is used again to detect the license plate, and a region of interest (ROI) is extracted from the image. The cv2.medianBlur function is applied to the ROI with a kernel size of 35, effectively blurring the license plate. The blurred ROI is then placed back into the original image, replacing the unblurred license plate.

Finally, the modified image with the blurred license plate is returned and displayed using the display function.

![image](https://github.com/user-attachments/assets/f406800e-90b0-49ab-9248-6f631317237f)
![image](https://github.com/user-attachments/assets/f8359f10-5fbb-40ae-af84-d1c1f0ac4383)
