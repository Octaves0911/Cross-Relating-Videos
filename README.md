# Cross Correlate Two Events Captured in Two Camera 

This project is build to relate two events that has been recorded in two different cameras. It has a wide range of applications in the surveillence sector. This model will give the time of the events occuring in each of the video frame and also provides the time difference between the corresponding events in the two videos.

# Technologies Used:
* Mean Squareed Error to calculate the difference between the two frames of the video that results in a cost that can be used to indicate an event.
* YOLO to track the object in the another frame
* deep-sort to track the objects
* easy ocr to detect the timestamp of the current frame

# Getting Started

1. Craete a virtual environment with CUDA enabled version.

``` 
conda env create -name cross_relate
conda activate cross_relate
```

2. Clone this repository to your local system

```
git clone https://github.com/Octaves0911/cross_relating_videos.git
```
4. Download all the dependencies as mentioned in the requirements.txt file.

``` 
pip install -r requirements.txt

```
3. Store the two video in the ./data/video/ as test1 and test2

4. Then run the object tracker python file. by passing the path of the video as the command line arguments and some other argument as mentioned below.

```
#To hide the processing of the frames

python object_tracker.py --video ./data/video/test1 --video1 ./data/video/test2.py --model yolov4 --info --dont_show

# To show the frames along with the processing

python object_tracker.py --video ./data/video/test1 --video1 ./data/video/test2.py --model yolov4 --info

```
5. The output will be stored in a json file named as output.json that will contain the following details:
* The time of event 1
* The time of event 2
* The time diffrerence between the two corresponding events

6. The output of the tracked will be stored in ./outputs

# Future Work:
This model can be made better by training it for anamoly detection. This would involve using an autoencode and train ot on UCF dataset for anomaly detection. Here we will be using training our model on the normal as well as anomolus videos and then using it to detect any anomaly in the video and capturing the timestamp of the event and then comparing it with the recorded timestamp of the corresponding video.
