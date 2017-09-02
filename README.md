[//]: # (Image References)

[image1]: ./runs/1504322468.821728/uu_000016.png
[image2]: ./runs/1504322468.821728/uu_000088.png
[image3]: ./runs/1504322468.821728/uu_000092.png

# Semantic Segmentation
### Introduction
In this project, we'll label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Setup
##### Frameworks and Packages
Make sure the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module. More details can be found in the section of Build the Neural Network as well as in script comments.

##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Build the Neural Network
The following functions are implemented.

- load_vgg: load VGG-16 model and weights
- layers: define FCN architecture
- optimize: define loss, optimizer and train operation
- train_nn: define training process

The cross entropy loss of the network will be printed while training.

### Neural Network Training
On average, the model decreases loss over time, as seen in the loss record file `training_loss.txt`.

| Epoch  | Average training loss  |
|:------------- |:---------------|	
|0|	10.109999656677246|
|1|	2.194674518281613|
|2|	0.669635089004741|
|3|	0.48282200541463277|
|4|	0.22459403273349815|
|5|	0.17198697745696895|
|6|	0.14638279842464155|
|7|	0.1285497673423026|
|8|	0.11635604289370012|
|9|	0.1039922225923893|
|10|	0.09642606084863413|

After trial, set hyper-parameters as below for better performance:

- number of epochs: 10
- batch size: 1
- learning rate: 1e-4
- keep probability: 0.5
- scalar multiplier for regularization: 1e-3

This project labels most pixels of roads close to the best solution. 

![alt text][image1]
![alt text][image2]
![alt text][image3]