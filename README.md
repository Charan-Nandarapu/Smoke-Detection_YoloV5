# Jetson_AIDsys
Animal Intrusion Detection system, a deep learning model developed on Yolov5 .It is trained and deployed on NVIDIA Jetson Nano kit

## Custom Object Detection(YOLOV5)

### Setting up Jetson Nano Kit:
 follow the page provided by Nvidia for quick setup:
 
 https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit
 
### Deepstream Installation:
Deepstream 6.0(most stable version we found):

https://docs.nvidia.com/metropolis/deepstream/6.0/dev-guide/text/DS_Quickstart.html

### Upgrading up Python 3.9

https://www.itsupportwale.com/blog/how-to-upgrade-to-python-3-9-0-on-ubuntu-18-04-lts/

### Setting up Yolov5:
https://github.com/ultralytics/yolov5

### Training the model:
Change the yaml file according to the classes of the data we have, and change the location of train and valid

Yaml file can be found at Yolov5/data/coco128.yaml

### Testing the model:

#### Detect.py:
open terminal and enter:

    python3 detect.py --weights best.pt --source 0
                                              0,1,2 -camera
                                              
                                              img.jpg
                                              
                                              video.mp4
                                              
                                              url

### Deepstream:

#### Generating weigths
1.Clone the Deepstrean-Yolo Repository

2.go to Deepstream-Yolo/utils/

3.copy gen_wts_YoloV5.py and paste to Yolov5 repo

4.enter the following command in the terminal for generating weights and cfg file:

        python3 gen_wts_yoloV5.py -w best.pt
5.create a folder for inference

6.Copy  generated weights and config files and paste the in yolov5

7.copy and paste deepstream config files into the folder created

8. Edit the config files accordingly

Run the Deepstream-app using following command:

        sudo deepstream-app -c animal_config.txt


## Output:

### Image Inference:
![image](https://user-images.githubusercontent.com/91280385/191220894-0f6c789b-426e-4bf3-bffd-d79d0bbd5278.png)

### Video Inference:


### Live Inference(Camera) on Jetson: 

### Using Deepstream:



https://user-images.githubusercontent.com/91280385/191314739-a6f7e113-42d6-4bdd-bf4d-ec546a6ea5ff.mp4
