# Object_Detection_TensorflowModel
Object detection using Tensorflow python library from the input images.

The TensorFlow Object Detection API is an open source framework built on top of TensorFlow that makes it easy to construct, train and deploy object detection models. At Google we’ve certainly found this codebase to be useful for our computer vision needs, and we hope that you will as well.



STEPS:

1) Create .xml of .jpg using "windows_v1.7.0_LableImg" tool.

2) Convert .xml to .csv by running  "xml_to_csv.py"

3) Generate TFrecord by running "generate_tfrecord.py"

4) Now required files are "Model" and "Configuration file"

5) Clone Object Detection API model from github
	link => https://github.com/tensorflow/models.git

6) Download Pre-trained model
	link => https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md

7) Configuration of pipeline.config

8) Move Data, Images, ssdModel, Configuration file and pbtxt file to Obj.Detection module.

9) Start retraining
	$ python D:\project\tensorflow\models-master\research\object_detection\train.py --logtostderr --train_dir=data\ --pipeline_config_path=data\ssd_mobilenet_v1_pets.config

10) Watch Training in TensorBoard
	$ tensorboard --logdir='data'

11) Export Inference Graph
	$  python D:\project\tensorflow\models-master\research\object_detection/export_inference_graph.py  --input_type image_tensor --pipeline_config_path data\ssd_mobilenet_v1_pets.config --trained_checkpoint_prefix data\model.ckpt-10000 --output_directory object_detection_graph

12) Open Jupyter Notebook to run “object_detection_tutorial.ipynb”

Output with detected cricket_ball in image.

![screenshot 824](https://user-images.githubusercontent.com/32256364/42319967-4a47939a-8071-11e8-953f-8c8212e12a1d.png)
![screenshot 825](https://user-images.githubusercontent.com/32256364/42319968-4a755c4e-8071-11e8-8038-50484baf96a5.png)
![screenshot 826](https://user-images.githubusercontent.com/32256364/42319969-4aa1cdba-8071-11e8-9bd4-1ee758a81c81.png)
![screenshot 827](https://user-images.githubusercontent.com/32256364/42319970-4b092a96-8071-11e8-97fc-ae078288ce79.png)
![screenshot 828](https://user-images.githubusercontent.com/32256364/42319971-4b45bf92-8071-11e8-9104-f9f8e1f7395c.png)
![screenshot 829](https://user-images.githubusercontent.com/32256364/42319972-4bf9b6c8-8071-11e8-839c-262ab7042e78.png)
![screenshot 830](https://user-images.githubusercontent.com/32256364/42319973-4c2ae342-8071-11e8-96ee-dbae149faec2.png)
![screenshot 831](https://user-images.githubusercontent.com/32256364/42319975-4cf0ecfe-8071-11e8-85e7-8c39818dbb8f.png)
