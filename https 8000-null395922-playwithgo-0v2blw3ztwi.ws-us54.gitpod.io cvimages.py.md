# https://8000-null395922-playwithgo-0v2blw3ztwi.ws-us54.gitpod.io/cvimages.py
[](https://8000-null395922-playwithgo-0v2blw3ztwi.ws-us54.gitpod.io/cvimages.py) 

 import cv2
import os

image_base_path = "images";

def get_images(video_path):
    frame_times = -1;
    fileName = video_path.split("\\\\")\[-1:]\[0].split('.')\[0]
    image_out_path = image_base_path + fileName
    if not os.path.exists(image_out_path):
        os.makedirs(image_out_path) 

    cap = cv2.VideoCapture(video\_path)
    while cap.isOpened():
        frame\_times = frame\_times + 1
        success, frame = cap.read()
        if not success:
            break;

        cv2.imencode('.jpg', frame)\[1\].tofile( str(frame\_times) + ".jpg")

if \_\_name\_\_ == '\_\_main\_\_':
    get_images('008.mp4')
