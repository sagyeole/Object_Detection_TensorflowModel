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
