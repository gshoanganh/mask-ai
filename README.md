# Mask object detection AI using the latest YOLOv5 model
<p>👋 Hello! This set of Notebooks was written to serve as a template for future AI projects. </p>
<p>Today, there are many models to develop AI with object detection projects. But Yolov5 is becoming the most powerful and fast. After many tries with different models, I feel that you should use Yolov5 to develop your Object Detection project.</p> 
📚 This guide explains how to train your own custom dataset with YOLOv5 🚀<br/>
🍀 Author: <b>Gs Hoang Anh</b> (<a href="https://www.youtube.com/c/GsHoangAnh">YouTube channel</a>.)
<br/>
<img width="500" src="https://github.com/gshoanganh/mask-ai/blob/main/photos/detect-page.jpg?raw=true"> 
<br/>

## Before You Start

<p>- install: <a href="https://www.python.org">Python>=3.7.0</a> 🌟</p>
<p>- Organize Directories: create folder "mask-ai"</p>
<p>
+ data/(images,labels): Include the image and the folder used to hold the txt file (tag label) <br/>
+ Training: This is a file for writing python code, code for training.
</p>
<img src="https://github.com/gshoanganh/mask-ai/blob/main/photos/directories01.png?raw=true"> 

## Prepare images and Create Labels

<b>Step 1</b>. You need to prepare about more than 20 images for more favorable training results.
<br/> note: after you have the images, add them to "mask-ai\data\images\(train,val)" folders. 
<br/>
<b>Step 2</b>. Create labels for images by visiting the website: <a href="https://www.makesense.ai/">makesense.ai</a>.
<br/> note: Of course you can also use other tools to assign your own labels. Example: imagelabel, Use Roboflow to label, ....
<br/>
<b>Step 3</b>. After successfully exporting the txt files, add them to the directory: "mask-ai\data\labels\(train,val)"

<pre>
python -m venv tfod
</pre> 
<br/><br/>
<b>Step 1.</b> Clone this repository: https://github.com/gshoanganh/facepen
<br/><br/>
<b>Step 2.</b> Create a new virtual environment 
<br/> cd facepen, run:
<pre>
python -m venv tfod
</pre> 
<br/>
<b>Step 3.</b> Activate your virtual environment
<pre>
source tfod/bin/activate # Linux
.\tfod\Scripts\activate # Windows 
</pre>
<br/>
<b>Step 4.</b> Install dependencies and add virtual environment to the Python Kernel
<pre>
python -m pip install --upgrade pip
pip install ipykernel
python -m ipykernel install --user --name=tfod
</pre>
<br/>
<b>Step 5.</b> Collect images using the Notebook <a href="#">1. Image Collection.ipynb</a> - ensure you change the kernel to the virtual environment as shown below 
<br/>
<b>Step 6.</b> Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders. <br/>
<pre>
\TFODCourse\Tensorflow\workspace\images\train<br />
\TFODCourse\Tensorflow\workspace\images\test
</pre>
<br/><br/>
<b>Step 7.</b> Begin training process by opening <a href="#">2. Training and Detection.ipynb</a>, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 
<br /><br/>
<b>Step 8.</b> During this process the Notebook will install Tensorflow Object Detection. You should ideally receive a notification indicating that the API has installed successfully at Step 8 with the last line stating OK.  

If not, resolve installation errors by referring to the <a href="#">Error Guide.md</a> in this folder.
<br /> <br/>
<b>Step 9.</b> Once you get to step 6. Train the model, inside of the notebook, you may choose to train the model from within the notebook. I have noticed however that training inside of a separate terminal on a Windows machine you're able to display live loss metrics. 

<br />
<b>Step 10.</b> You can optionally evaluate your model inside of Tensorboard. Once the model has been trained and you have run the evaluation command under Step 7. Navigate to the evaluation folder for your trained model e.g. 
<pre> cd Tensorlfow/workspace/models/my_ssd_mobnet/eval</pre> 
and open Tensorboard with the following command
<pre>tensorboard --logdir=. </pre>
Tensorboard will be accessible through your browser and you will be able to see metrics including mAP - mean Average Precision, and Recall.
<br />
<br />
<p>© Gs Hoang Anh</p>