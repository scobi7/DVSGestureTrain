
Technical Report
	Spiking Neural Networks are a deep-learning model that communicates and shows output by spikes. SNNs are great for learning neuromorphic and time-based datasets because of their energy efficiency and how easy it is to fine-tune hyperparameters. 
	I chose the DVS Gesture data set to solve using SNNs. The task for this was to create a Sequential Network compromised of 2 sets of convolutional layers and a LIF layer. We also define a feed-forward function that iterates through the data and returns them as a tensor. This all is used by the training loop that creates a spike from the input data using the Sequential Network. This was my architecture for SNNs.
	I got a good amount of the tutorial done. I was able to “train” very inaccurately and inconsistently. The first challenge I faced was transforming the dataset. I kept trying to use Resize() and ToFrame() both from different libraries to transform my data. They were incompatible so I was unable to transform this way. It was easily fixed by just changing the sensor_size, and then correctly using data loaders to execute this change. The next issue I had was with layer sizes and dimension compatibility. Issues with multiplying mat1 and mat2 most stemmed from how I defined the layers in your network (the numbers and sizes of them). I made sure your input tensor size matches the expected input size of the linear layer by tweaking the sizes of the second layer to match the size of my flattened linear layer and it worked. The last issue I had was training. I could not figure out an optimal batch size, number of iterations, or epochs to effectively solve this dataset. Besides the fact that the numbers seemed to not go in the right direction even after around 40 iterations, I could not fully run a large trial without running out of RAM/GPU.
	This leads me to the future. To successfully fix this issue, I may have to use a validation data set to tune my hyperparameters easier. I think using something like this will allow me to save GPU storage and test my parameters more efficiently to figure out a working set. Although not finished, I am pretty proud of my progress because I started late, and was able to get a lot done for the other climbing dataset project I was working on at first. 
	I can see myself working to perfect and continue developing my climbing dataset project. I hope to create a fully working and strong dataset and be able to successfully create an SNN architecture to solve the dataset.  
Github Repos:

https://github.com/scobi7/CruxCam
https://github.com/scobi7/DVSGestureTrain

References:

Jason K. Eshraghian, Max Ward, Emre Neftci, Xinxin Wang, Gregor Lenz, Girish Dwivedi, Mohammed Bennamoun, Doo Seok Jeong, and Wei D. Lu. "Training Spiking Neural Networks Using Lessons From Deep Learning". Proceedings of the IEEE, 111(9) September 2023.
