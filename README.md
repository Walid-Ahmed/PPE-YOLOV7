# PPE-YOLOV7

This code is designed through pipelining YOLOV7 models to detect whether the workers at a construction site are wearing safety helmets or not.



<h3>Installation:</h3> 
<li>git clone https://github.com/Walid-Ahmed/PPE-YOLOV7 -- Used to clone this repo 
<li>cd PPE-YOLOV7 -- moves you into the folder  
<li>pip install -r requirements.txt ---installs all the needed libraries
<li>if needed pip install torchvision==0.9.1  and pip install "opencv-python-headless<4.3"
 
<h4>You Can Simply Run The Code Using PPE-YOLOV7.ipynb by running it through either jupiter or colab.</h4>
        
<h3>Running the code:</h3> 

<h2>Images</h2> 
<li>python detect.py --weights yolov7.pt --weights2 Helmet.pt --conf 0.3 --class 0  --object 0  --source Test.jpg 

Where : yolov7.pt is the model used to detect person
        Helmet.pt is the model used to detect helmet
        Test.jpg is the Name of the file you want to detect ex. image.jpg/video.mp4
        conf 0.3 is the confidence threshold 
        class 0 is so yolov7.pt detects only persons
        object 0 is so Helmets.pt checks for only helmets  
        NOTE : if the models/image/video path is not directly yolov7 you should put the path instead 

<li> After A Successful run a folder is created "runs" you go into 'detect' and then the latest exp file ex. 'exp4' to find your output.
 

![FinalImage](https://user-images.githubusercontent.com/20994789/200956605-385ffd4e-d3a6-4a16-a69a-2397acf03995.png)


And :![39e3504d-347e-4a57-83b2-ec07d5835448](https://user-images.githubusercontent.com/20994789/200872830-079af635-de7d-460e-9278-90131bf61e57.jpg)
        
The Code Produces A Text File With A Report On Every Frame Given: 
and the output text file included:

Frame 1 :  3 People Wearing Helmets , Not Wearing Helmets.


<h2>Videos</h2> 
You can also run this code on a video using TestVideo.mp4
<li>python detect.py --weights yolov7.pt --weights2 Helmet.pt --conf 0.3 --class 0  --object 0  --source TestVideo.mp4


Where : yolov7.pt is the model used to detect person
        Helmet.pt is the model used to detect helmet
        Test.jpg is the Name of the file you want to detect ex. image.jpg/video.mp4
        conf 0.3 is the confidence threshold 
        class 0 is so yolov7.pt detects only persons
        object 0 is so Helmets.pt checks for only helmets  
        NOTE : if the models/image/video path is not directly yolov7 you should put the path instead 

<li> After A Successful run a folder is created "runs" you go into 'detect' and then the latest exp file ex. 'exp4' to find your output.


![FinalResult](https://user-images.githubusercontent.com/20994789/200954590-c2b7824f-c39a-43e4-b3ce-82ea148d7450.gif)


And Text File : 
[TestVideo.txt](https://github.com/Walid-Ahmed/PPE-YOLOV7/files/9975597/TestVideo.txt)


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
 



