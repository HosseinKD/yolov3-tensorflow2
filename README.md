# YOLO v3 in Tensorflow 2.0

Implementation of YOLO v3 object detector in Tensorflow 2.0 (Keras). This code is basically based on [YangYun](https://github.com/YunYang1994/tensorflow-yolov3). 

Tested on Python 3.6, Tensorflow 2.0 alpha on Ubuntu 16.04.

## Todo list:
- [x] YOLO v3 architecture
- [ ] Basic working demo
- [ ] Weights converter (util for exporting loaded COCO weights as TF checkpoint)
- [ ] Training pipeline
- [ ] More backends

## Reference
[Paweł Kapica
](https://github.com/mystic123/tensorflow-yolo-v3) and his [post](https://itnext.io/implementing-yolo-v3-in-tensorflow-tf-slim-c3c55ff59dbe)

## How to run the demo:
To run demo type this in the command line:

1. Download COCO class names file: `wget https://raw.githubusercontent.com/pjreddie/darknet/master/data/coco.names`
2. Download and convert model weights:    
    1. Download binary file with desired weights: 
        1. Full weights: `wget https://pjreddie.com/media/files/yolov3.weights`
        1. Tiny weights: `wget https://pjreddie.com/media/files/yolov3-tiny.weights` 
    2. Run `python ./convert_weights.py` and `python ./convert_weights_pb.py`        
3. Run `python ./demo.py --input_img <path-to-image> --output_img <name-of-output-image> --frozen_model <path-to-frozen-model>`


####Optional Flags
1. convert_weights:
    1. `--class_names`
        1. Path to the class names file
    2. `--weights_file`
        1. Path to the desired weights file
    3. `--data_format`
        1.  `NCHW` (gpu only) or `NHWC`
    4. `--tiny`
        1. Use yolov3-tiny
    5. `--ckpt_file`
        1. Output checkpoint file
2. convert_weights_pb.py:
    1. `--class_names`
            1. Path to the class names file
    2. `--weights_file`
        1. Path to the desired weights file    
    3. `--data_format`
        1.  `NCHW` (gpu only) or `NHWC`
    4. `--tiny`
        1. Use yolov3-tiny
    5. `--output_graph`
        1. Location to write the output .pb graph to
3. demo.py
    1. `--class_names`
        1. Path to the class names file
    2. `--weights_file`
        1. Path to the desired weights file
    3. `--data_format`
        1.  `NCHW` (gpu only) or `NHWC`
    4. `--ckpt_file`
        1. Path to the checkpoint file
    5. `--frozen_model`
        1. Path to the frozen model
    6. `--conf_threshold`
        1. Desired confidence threshold
    7. `--iou_threshold`
        1. Desired iou threshold
    8. `--gpu_memory_fraction`
        1. Fraction of gpu memory to work with