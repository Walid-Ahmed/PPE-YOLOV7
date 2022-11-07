# PPE-YOLOV7

This code is designed through pipelining YOLOV7 models to detect whether the workers at a construction site are wearing safety helmets or not.



<h3>Installation:</h3> 
<li>git clone https://github.com/Walid-Ahmed/PPE-YOLOV7 -- Used to clone this repo 
<li>cd PPE-YOLOV7 -- moves you into the folder  
<li>pip install -r requirements.txt ---installs all the needed libraries
<li>if needed pip install torchvision==0.9.1  and pip install "opencv-python-headless<4.3"

<h3>Running the codeL</h3> 
<li>python detect.py --weights yolov7.pt --weights2 Helmet.pt --conf 0.3 --class 0  --object 0  --source Test.jpg 

Where : yolov7.pt is the model used to detect person
        Helmet.pt is the model used to detect helmet
        Test.jpg is the Name of the file you want to detect ex. image.jpg/video.mp4
        conf 0.3 is the confidence threshold 
        class 0 is so yolov7.pt detects only persons
        object 0 is so Helmets.pt checks for only helmets  
        NOTE : if the models/image/video path is not directly yolov7 you should put the path instead 

<li> After A Successful run a folder is created "runs" you go into 'detect' and then the latest exp file ex. 'exp4' to find your output.

In this case the output was:![image](https://user-images.githubusercontent.com/20994789/199857591-16dfe955-b4e5-43ec-96d8-1c4cca14308c.png)

You can also run this code on a video using TestVideo.mp4

 ![Test](https://user-images.githubusercontent.com/20994789/199861245-00aed46f-9068-416d-96de-a47948a44b6f.gif)

        <h3>Training the model :</h3>

 To train the model you need to provide a dataset in the type yolov7 where annotaions are stored in .txt files
 
1. clone the repo into your colab
2. wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7_training.pt
3. python train.py --batch 12 --epochs 10 --data [yamlfile] --weights yolov7_training --device 0 --to train your model
   model will be stored in 'runs'-->'train'-->the latest 'exp' folder --> 'weights'-->best.pt
4. python detect.py --weights runs/train/exp/weights/best.pt --conf 0.1 --source Test.jpg -- to test your output and confidence 

Where :  --batch is batchsize 
         --epochs is the number o epochs you want to train the model
         --data the path of the yaml file in your dataset
         --wieghts pre set weights for training
         --device 0 in case gpu and cpu in case of cpu
 



