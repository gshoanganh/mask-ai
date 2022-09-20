# Mask object detection AI using the latest YOLOv5 model
<p>👋 Hello! This set of Notebooks was written to serve as a template for future AI projects. </p>
<p>Today, there are many models to develop AI with object detection projects. But Yolov5 is becoming the most powerful and fast. After many tries with different models, I feel that you should use Yolov5 to develop your Object Detection project.</p> 
📚 This guide explains how to train your own custom dataset with YOLOv5 🚀<br/>
🍀 Author: <b>Gs Hoang Anh</b> (<a href="https://www.youtube.com/c/GsHoangAnh">Youtube channel</a>.)
<br/>
<br/>
<img width="630" src="https://github.com/gshoanganh/mask-ai/blob/main/photos/detect-page.jpg?raw=true"> 
<br/>

## Before You Start

<p>- install: <a href="https://www.python.org">Python>=3.7.0</a> 🌟</p>
<p>- Organize Directories: create a folder <code>mask-ai</code> is your project.</p> 
<p>
<i>+ <code>data/(images,labels)</code>: Include the image and the folder used to hold the txt file (tag label)</i> <br/>
<i>+ <code>Training</code>: This is a file for writing python code, code for training.</i>
</p>
<img src="https://github.com/gshoanganh/mask-ai/blob/main/photos/directories01.png?raw=true"> 
<br/>
Data should be well labeled as yolo format and store in the path of training/validation data defined previously.
<br/>
- In the directory, you should have to folder of images and labels:
<br/>In each folder, you shold have <code>train</code> and <code>val</code> folders that contains the same numbers of items in both images and labels.
<br/><br/>

> 💡 ProTip: You can skip this step by cloning my project <code>git clone https://github.com/gshoanganh/mask-ai.git </code>

## Yolov5

<b>Step 1</b>. From <code>mask-ai</code> folder, run the command:

~~~
git clone https://github.com/ultralytics/yolov5
~~~
<br/>
<img src="https://github.com/gshoanganh/mask-ai/blob/main/photos/directories02.png?raw=true"> 

<b>Step 2</b>. Modify path of data and classes
<p>Find file path at <code>yolov5/data/coco128.yaml</code>, duplicate an new file and rename as <code>comask.yaml</code></p>
<p>Open the file and modify our config as follows</p>

~~~
train: ../train_data_new/images/train/  # path of training data
val: ../train_data_new/images/val/  # path of validation data
test:  # test images (optional)

# Classes
nc: 2  # number of classes
names: ['mask','notmask']  # class names
~~~

## Prepare images and Create Labels

<b>Step 1</b>. You need to prepare about more than 20 images for more favorable training results.
<br/> <i>note: after you have the images, add them to <code>mask-ai\data\images\\(train,val)</code> folders. </i>
<br/>
<b>Step 2</b>. Create labels for images by visiting the website: <a href="https://www.makesense.ai/">makesense.ai</a>.
<br/> <i>note: Of course you can also use other tools to assign your own labels. Example: imagelabel, Use Roboflow to label, ....</i>
<br/>
<b>Step 3</b>. After successfully exporting the txt files, add them to the directory: <code>mask-ai\data\labels\\(train,val)</code>


## Getting started


<b>Step 1</b>. Activate env
<p>From <code>smoke-ai</code> folder, open command:
<pre>
python -m venv yolo #method1
python3 -m venv yolo #method2
</pre> 
<br/>  
<b>Step 2.</b> Activate your virtual environment
<pre>
source yolo/bin/activate # Linux/Mac
.\yolo\Scripts\activate # Windows 
</pre>
<br/>
<b>Step 3.</b> Install dependencies and add virtual environment to the Python Kernel
<pre>
python -m pip install --upgrade pip
pip install ipykernel
python -m ipykernel install --user --name=yolo
</pre>

> 💡 Bug: You can use <code>pip2</code> </note>
<br/>
<b>Step 4.</b> install all requirements
<pre>
cd yolov5
install requirements.txt
</pre>

<b>Step 5.</b> Run notebook
<pre>
cd ..
python3 notebook
</pre>

> 💡 Warning: In this step, you will perform some checks to see if the default yolov5 is running correctly.

<b>Step 6.</b> TRAINING...
<P>Open a new tab command, then repeat step 1 and step 2 again </p>
<p>next, run: </p>
<pre>
python train.py --img 640 --batch 3 --epochs 100 --data ccmask.yaml --weights yolov5l.pt --cache --worked 2
</pre>
<p>If you have GPU usage. Please run:</p>
<pre>
python train.py --img 640 --batch 3 --epochs 100 --data ccmask.yaml --weights yolov5l.pt --cache --device 0
</pre>
Good luck ☘️
<br /><br/>
<p>© Gs Hoang Anh</p>