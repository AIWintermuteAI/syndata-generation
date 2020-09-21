# SynDataGeneration 

This code is used to generate synthetic scenes for the task of instance/object detection. Given images of objects in isolation from multiple views and some background scenes, it generates full scenes with multiple objects and annotations files which can be used to train an object detector. The approach used for generation works well with single-shot detectors like YOLO and SSD.

## Pre-requisites 
Install from requirements.txt with
pip install -r requirements.txt

## Setting up Defaults
The first section in the defaults.py file contains paths to various files and libraries. Set them up accordingly.

The other defaults refer to different image generating parameters that might be varied to produce scenes with different levels of clutter, occlusion, data augmentation etc. 

## Running the Script
```
python dataset_generator.py [-h] [--selected] [--scale] [--rotation]
                            [--num NUM] [--dontocclude] [--add_distractors]
                            root exp

Create dataset with different augmentations

positional arguments:
  root               The root directory which contains the images and
                     annotations.
  exp                The directory where images and annotation lists will be
                     created.

optional arguments:
  -h, --help         show this help message and exit
  --selected         Keep only selected instances in the test dataset. Default
                     is to keep all instances in the roo directory.
  --scale            Add scale augmentation.Default is to not add scale
                     augmentation.
  --rotation         Add rotation augmentation.Default is to not add rotation
                     augmentation.
  --num NUM          Number of times each image will be in dataset
  --dontocclude      Add objects without occlusion. Default is to produce
                     occlusions
  --add_distractors  Add distractors objects. Default is to not use
                     distractors
```

## Training an object detector
For complete example on training lego detector with synthetic data, have a look at my article on Hackster.io.

## Paper

The code was used to generate synthetic scenes for the paper [Cut, Paste and Learn: Surprisingly Easy Synthesis for Instance Detection](https://arxiv.org/abs/1708.01642). 

If you find our code useful in your research, please consider citing:
```
@InProceedings{Dwibedi_2017_ICCV,
author = {Dwibedi, Debidatta and Misra, Ishan and Hebert, Martial},
title = {Cut, Paste and Learn: Surprisingly Easy Synthesis for Instance Detection},
booktitle = {The IEEE International Conference on Computer Vision (ICCV)},
month = {Oct},
year = {2017}
}
```
