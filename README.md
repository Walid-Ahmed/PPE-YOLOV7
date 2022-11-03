# PPE-YOLOV7

1 . Download The Repo onto your device / google colab using :

!git clone https://github.com/Walid-Ahmed/PPE-YOLOV7


2 . Run this few commands to download the requirments : 

%cd yolov7
!pip install -r requirements.txt

3. Run the project using : 
!python detect.py --weights yolov7.pt --weights2 Helmet.pt --conf 0.3 --class 0  --object 0  --source [Image/Video Name]


Where : yolov7.pt is the model used to detect person
        Helmet.pt is the model used to detect helmet
        Image Name is the Name of the file you want to detect ex. image.jpg/video.mp4
        conf is the confidence threshold 
        class is so yolov7.pt detects only persons
        object is so Helmets.pt checks for only helmets  
        NOTE : if the models/image/video path is not directly yolov7 you should put the path instead 
