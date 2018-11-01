VizTransfert
=====
Project description
-----
The directory allows from an image database containing 3 different classes to drive a GAN network model and generate images based on the same style by the trained model.
From a database containing 3 image classes of any size and format, each image is resized to size 256x256 and converted to JPG. And then the contours are extracted as a black and white image. In the end, we combine them like the training data set and the test.
We put 4 files in this directory:



•/google_pictures contains 3 types of images (bar chart,line chart et scatter plot).

•/data/dst contains 3 directories of images ready to be used as training data for the GAN model.

•/pix2pix-master is a forked repo from https://github.com/phillipi/pix2pix written in lua.

•/pytorch-CycleGAN-and-pix2pix is a forked repo from https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix written in python.

•/résultat contains observed results.
		
From the /data folder, we distribute our images. This will be read to drive the neural network. At the end of the training, which can be longer or shorter depending on the parameters you have chosen, the model is saved.
It is then used automatically on the folder/test created later and creating a results folder. In its subfolder latest_net_G_val, you can see the results in the web index.html.
As each intermediate variable is recorded (trained GAN model), it is possible to reuse them to generate images without performing all the steps.


Image processing
--------
In order to install all the packages needed to run the script, run construct.py to change the image size, extract the outline as a black and white image and combine the original image pairs and outline images into a series of images. This is to create a /data/src folder. The src folder must contain its own train, val, test, etc. subfolders. Put the original images in /data/src/train, /data/src/val and /data/src/test. And then execute the command below:

`python construire.py --fold_src data\src --fold_dst data\dst`

After the script is executed, 3 "test", "train" and "val" files are created in data\dst. This contains the data set size 256x128 for a pair of images to be trained and tested. 
Finally, we follow the launch of git pix2pix to get the result.



Authors
-------------
		Théo Jaunet
		Romain Vuillemot
	with help from :
		LIU Xiang
		He Yitong

