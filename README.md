#### Autonomous vehicle research and projects

##### i. Obstacle classification in images using deep learning
* Developed an image classifier model and studied response time for obstacles, trained with CIFAR-10 and with real-time image scans using Theano/Lasagne.
* Deployed upon Amazon EC2 and studied the GPU-enabled performance of the network, which showed improved processing by a factor of 10.

##### ii. Drive-by-wire Steering Design
* Designed a simulation model for the steering mechanism of an autonomous car, employing a Drive-by-Wire mechanism and deployed on the Simulink environment (CarSim, PreScan, and SimScape).
* Proposed a model with Nissan ECU unit and multiple sensors upon a Power Assisted Steering mechanism, after test simulations for constant and variable speeds. Studied torsion, yaw and acceleration parameters.

##### iii. [Real-time Speed Detection from Visual Video Feed](https://github.com/bongam12/speedPrediction)
* Developed a velocity prediction and calibration system based on dashcam video data, using RCNNs and MobileNet SDD architecture.
* Explored end-to-end approach with Optical flow upon OpenCV, with the training module developed upon Pytorch.


**Tools used:** (PyTorch, OpenCV, MobileNet SSD, Matlab, Simulink, CAD, Mechanics, ECU, Theano, Lasagne, Nolearn, EC2)

___

<img src="https://github.com/govindarajula/btech/blob/master/images/model%20idea.jpg" width="400"> <img src="https://github.com/bongam12/speedPrediction/blob/master/dl-opt-flow/output.gif" width="300">


Footnotes:

    Network-in-network layers: These are small neural networks that are easier to interpret than traditional
    neural network layers.
    Dropout layers: These randomly drop units during training, preventing overfitting, which is a major problem
    in neural networks.
    Noise layers: These introduce noise into the neurons; again, addressing the overfitting problem.


> Detailed notes of Project (iii)

#### Intro

Our submisison expands to three sections and has worked on a speed detection challenge, attainign promising results with enough scope to expand beyond the videos, towards real-time use and for working more on advanced DNN models.

> Download the files for training and testing (data folder) from the comma.ai GitHub [repository](https://github.com/commaai/speedchallenge).

#### Pipeline and architecture:
Main Tools: Caffe, PyTorch, CNNs, Single-shot MultiBox detectors, OpenCV

<img src="dl-opt-flow/nvidia.jpg">

1. DL model - initial architecture & training
* To begin our exploration, we decided to start with a basic 8 layer convulational neural net. This net structure is an adaption of tensor flows implementation of a convolution net. However, instead of using the exact net structure, we altered its input dimension and output dimensions as well as its convolution layers in order to successful run our model on our video dataset. 
* The results of the model can be found at the bottom of the the "Speed Prediction DL.ipnyb" in the file "DLNotebook". The overall performance of this model indicated that there was not a significant predictive aspect of the model. 

 <img src="dl-opt-flow/layers.png" width="300">

2. Using Optical Flow (MSE ~5)

* This approach has expanded upon the baseline model and incorporated the techniques from Nvidia's [paper](https://arxiv.org/pdf/1604.07316.pdf) for object detection, mainly capitalizing on Optical Flow and image transformations to train the Neural Net.

i. Harnessing optical flow and training from consecutive image captures from video

ii. Incorporation of Multi-box detection & future work towards Real time detection

<img src="dl-opt-flow/comparison.png" width="300"> <img src="dl-opt-flow/output.gif" width="350">

* After initial training and preprocessing, we observe that consectuive and multiple images are better than single images, pulled from the mp4 file.

3. Linear Regression Model

* Apart from DL curiosity and above models, we explored a bare-bones architecture built for object detection, and these files are available in the 'linearRegression' folder.
* This model has achieved an MSE value close to 6, but has used significantly lesser compute power. However, we see merit in expanding more for stage 2 model towards real-time detection with Caffe support.

<img src="lin-reg/train_graph.png" width="300"> <img src="lin-reg/validation_graph.png" width="300">

#### Implementation

1. Explore the ipynb and supported .py files

2. Ensure the supported libraries are installed (argparse, OpenCV/cv2, numpy)

* Kindly refer to final-rerun.py file for looking at our model. All the comments illsutrate each section from preprocessing, training and testing, with results saved in the 'dl-opt-flow' folder.
* For explanding and studying real-time detection, please see:
> python comma_play.py --video train.mp4

For this case, the pre-trained model and weidhts are needed, from MobileNetSSD, available online.

3. Please refer to solvers.py file and the generated graphs in lin-reg directory
