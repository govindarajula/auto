#### Autonomous vehicle research and projects

##### i. Obstacle classification in images using deep learning
* Developed an image classifier model and studied response time for obstacles, trained with CIFAR-10 and with real-time image scans using Theano/Lasagne.
* Deployed upon Amazon EC2 and studied the GPU-enabled performance of the network, which showed improved processing by a factor of 10.

##### ii. Drive-by-wire Steering Design
* Designed a simulation model for the steering mechanism of an autonomous car, employing a Drive-by-Wire mechanism and deployed on the Simulink environment (CarSim, PreScan, and SimScape).
* Proposed a model with Nissan ECU unit and multiple sensors upon a Power Assisted Steering mechanism, after test simulations for constant and variable speeds. Studied torsion, yaw and acceleration parameters.

##### iii. Real-time Speed Detection from Visual Video Feed
* Developed a velocity prediction and calibration system based on dashcam video data, using RCNNs and MobileNet SDD architecture.
* Explored end-to-end approach with Optical flow upon OpenCV, with the training module developed upon Pytorch.


**Tools used:** (PyTorch, OpenCV, MobileNet SSD, Matlab, Simulink, CAD, Mechanics, ECU, Theano, Lasagne, Nolearn, EC2)

___

<img src="https://github.com/gvsakashb/btech/blob/master/images/model%20idea.jpg" width="500">
Footnotes:

    Network-in-network layers: These are small neural networks that are easier to interpret than traditional
    neural network layers.
    Dropout layers: These randomly drop units during training, preventing overfitting, which is a major problem
    in neural networks.
    Noise layers: These introduce noise into the neurons; again, addressing the overfitting problem.
