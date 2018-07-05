# Object_Detection_TensorflowModel
Object detection using Tensorflow python library from the input images.

The TensorFlow Object Detection API is an open source framework built on top of TensorFlow that makes it easy to construct, train and deploy object detection models. At Google we’ve certainly found this codebase to be useful for our computer vision needs, and we hope that you will as well.

Output with detected cricket_ball in image.

![screenshot 809](https://user-images.githubusercontent.com/32256364/42314336-6d5439a6-8062-11e8-98e8-ede186e3a0fe.png)
![screenshot 811](https://user-images.githubusercontent.com/32256364/42314337-6d85fb76-8062-11e8-8cc0-acf5e0479aef.png)
![screenshot 812](https://user-images.githubusercontent.com/32256364/42314338-6db72fac-8062-11e8-9155-7e698f9987ad.png)
![screenshot 813](https://user-images.githubusercontent.com/32256364/42314339-6de5b87c-8062-11e8-97d0-bf6c1596a6da.png)



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
