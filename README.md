# PPE-YOLOV7

This code is designed through pipelining YOLOV7 models to detect whether the workers at a construction site are wearing safety helmets or not.
Some limiting factors are that now the code detects if the helmet is anywhere within the bounding box of the worker , yet with simple code this could be overcomed .




1 . Download The Colab PPE-YOLOV7 and Run :

Code Rundown : 
1. git clone https://github.com/Walid-Ahmed/PPE-YOLOV7 -- Used to clone this repo into your colab notebook
2. !pip install -r requirements.txt & cd PPE-YOLOV7 -- moves you into the folder and installs all the needed libraries
3. python detect.py --weights yolov7.pt --weights2 Helmet.pt --conf 0.3 --class 0  --object 0  --source Test.jpg 

Where : yolov7.pt is the model used to detect person
        Helmet.pt is the model used to detect helmet
        Test.jpg is the Name of the file you want to detect ex. image.jpg/video.mp4
        conf 0.3 is the confidence threshold 
        class 0 is so yolov7.pt detects only persons
        object 0 is so Helmets.pt checks for only helmets  
        NOTE : if the models/image/video path is not directly yolov7 you should put the path instead 

2. After A Successful run a folder is created "runs" you go into 'detect' and then the latest exp file ex. 'exp4' to find your output.

In this case the output was:![image](https://user-images.githubusercontent.com/20994789/199857591-16dfe955-b4e5-43ec-96d8-1c4cca14308c.png)

You can also run this code on a video using TestVideo.mp4



Training the model :

 To train the model you need to provide a dataset in the type yolov7 where annotaions are stored in .txt files
 
 



