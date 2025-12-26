# 👤 Face Detection Project

This project is a **Face Detection system** developed to detect human faces in images or real-time video using computer vision techniques.  
The main goal of this project is to understand **image processing and face detection concepts**.

---

## 🎯 Project Objective

- To detect human faces accurately
- To learn the basics of computer vision
- To work with real-time image/video processing
- To gain hands-on experience with face detection algorithms

---

## 🚀 Features

- Detects faces in images
- Real-time face detection using webcam
- Draws bounding boxes around detected faces
- Simple and easy-to-use implementation

---

## 🛠️ Technologies Used

- Python  
- OpenCV  
- Haar Cascade Classifier  

*(Update this section if you used different tools)*

---

## 📂 Project Structure


import cv2
face_cap = cv2.CascadeClassifier("C:/Users/admin/AppData/Local/Programs/Python/Python313/Lib/site-packages/cv2/data/haarcascade_frontalface_default.xml")


video_cap = cv2.VideoCapture(0)

while True:
    ret, video_data = video_cap.read()
    if not ret:
        break  
    col = cv2.cvtColor(video_data, cv2.COLOR_BGR2GRAY)

   
    faces = face_cap.detectMultiScale(
        col,
        scaleFactor=1.1,
        minNeighbors=5,     
        minSize=(30, 30),
        flags=cv2.CASCADE_SCALE_IMAGE
    )

    
    for (x, y, w,h) in faces:
        cv2.rectangle(video_data, (x, y), (x +w, y +h), (0, 255, 0), 2)

   
    cv2.imshow("video_live", video_data)

   
    if cv2.waitKey(10) == ord("a"):
        break


video_cap.release()
