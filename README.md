# tf_Badminton IN-OUT Lineman Project
A project to read the in-out of badminton shuttlecock using the tensorflow object detection API  
Created on a Colab basis.  
Use tensorflow object detection API  

## 1. Setup
1) drive mount

## 2. Setting the Work Environment
2) import the models for object detection
* tensorflow ssd mobilenet
3) add tf libraries to pythonpath
4) download pre-trained model
* ssd_mobilenet_v2_quantized_300x300_coco_2019_01_03
## 3. Update model pipeline configurations

1.  model
*   Line 3: num_classes = number of classes in your dataset.
2.  train_config
*   Line 157: fine_tune_checkpoint = MODEL_DIR/training/model.ckpt
3.  train_input_reader
*   Line 162: label_map_path = MODEL_DIR/data/labelmap.pbtxt
*   Line 164: input_path = MODEL_DIR/data/train.record
4.  eval_config
*   Line 168: num_examples = number of test images
5.  eval_input_reader
*   Line 174: label_map_path = MODEL_DIR/data/labelmap.pbtxt
*   Line 178: input_path = MODEL_DIR/data/test.record

## 4. Train
* if ckpt-0: 37:36[click to run] ~ 39:35[activate first step] => about 2 min to start learning (2019-12-14)
* num_train_steps=100000

## 5. Tflite converting
title Download cocoapi_clone
* helped metrics per category successfully on github
* cocoapi_clone from some user for us
* Without it, 'export_tflite_ssd_graph.py' doesn't work
