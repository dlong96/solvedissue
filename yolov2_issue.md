
# YOLOV2 Pretrained Model Command Line Go Through

YOLOV2 is written in C, and the [github link](https://github.com/thtrieu/darkflow) here translates into to a tensorflow version. The details of how to use the it are already written, however, I faced a few problems when tried to run it on my terminals. For your infomation, I am using mac os.
The only sections from orginal github report you should look are **Getting started**, and **Training on your own dataset**.

The following are solutions that worked for me:<br/>
Download the repository from the link, navigate into the directory where darkflow-master is.

Before doing anything, use **-conda update all** to update all packages in current enviroment, hopefully this could save us a lot effort.

Next use one of the three given options, then you may see the error "No module name Cython", go ahead **-pip install Cython.
**<br/>
Run *flow --model cfg/cfg_you_picked.cfg --load bin/weight_downloaded_from_yolo.weights --train --annotation train/Annotations --dataset train/Images* <br/>
For people using their own dataset, If you have annotation file in voc format in xml file, you could directly use here. Otherwise, **Labelimg**, which is a pretty handy annotation tool, also provide txt file in YOLO required format.

Then you probably see the error 'no module named 'darkflow.cython_utils.cy_yolo_findboxes'. If you are window user, it requires to download 2017version visualstudio buildtool. If you are using mac, update packages automatically solve this issue.

Run the same command again , AssertionError may pop out' expect 64701556 bytes, found 680357512', the number of bytes may differ. Go to the cfg file in cfg folder, make sure the cfg file you are going to use have the same name as your downloaded weights file. After you set both same, your code is good to go.

Hope these could also help you.


