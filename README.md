# Urban-Sound-Classification-using-Deep-Learning
Automatic environmental sound classification is a growing area of research with numerous real world applications. Such as voice assistant can give medical recommendation when user sound sick and sending appropriate advertisements by analysis the size of the room size using user voice’s echo, automatic lower the music volume when there is an incoming call to the user and so on. There is a large body of research in related audio fields such as speech and music, but working on the classification of environmental sounds is comparatively scarce.
There is plenty of real world applications for this research, such as:
• Content-based multimedia indexing and retrieval
• Assisting deaf individuals in their daily activities
• Smart home use cases such as health care and user experience customization
• Industrial uses such as predictive maintenance.
 
Problem statement
The following will demonstrate how to apply Deep Learning techniques to the classification of environmental sounds, specifically focusing on the identification of particular urban sounds.
When given an audio sample in a wav file, of a few seconds duration, we want to be able to determine if it contains one of the target urban sounds with a corresponding Classification Accuracy score.
Data Set
This dataset contains 8732 labeled sound excerpts (<=4s) of urban sounds from 10 classes: 
air_conditioner
car_horn
Children_playing
dog_bark
drilling
enginge_idling
gun_shot 
jackhammer 
Siren
street_music.
A sample of this dataset is included with the accompanying git repo and the full dataset can be downloaded from here.

Wav file is stored in a way such that the sampling rate is 44.1kHz(44100 times per second).
Each sample is the amplitude of the wave at 1/44100 second=22.67us of interval, where the bit depth determines how detailed the sample will be also known as the dynamic range of the signal. For example, 16bit range means a sample’s has 2^16=65536 amplitude values with equal amplitude interval.

This project involves fundamental of digital signal processing(sampling, aliasing and Nyquist Theorem)

My initial approach is extract wav file so that the frequency components and bit depth components can be read , further analysis, training, and testing.

### Algorithms and Techniques:
The proposed solution to this problem is to apply Deep Learning techniques that have proved to be highly successful in the field of image classification.									
First we will extract Mel-Frequency Cepstral Coefficients (MFCC) from the audio samples on a per-frame basis with a window size of a few milliseconds. The MFCC summarises the frequency distribution across the window size, so it is possible to analyse both the frequency and time characteristics of the sound. These audio representations will allow us to identify features for classification. 
The next step will be to train a Deep Neural Network with these data sets and make predictions. We will begin by using a simple neural network architectures, such as Multi-Layer Perceptron before experimenting.

### Initial model architecture - MLP
We will start with constructing a Multilayer Perceptron (MLP) Neural Network using Keras and a Tensorflow backend.
Starting with a sequential model so we can build the model layer by layer.
We will begin with a simple model architecture, consisting of three layers: an input layer, a hidden layer and an output layer. All three layers will be of the dense layer type which is a standard layer type that is used in many cases for neural networks.
The first layer will receive the input shape. As each sample contains 40 MFCCs (Mel Frequency Cepstral Coefficients)(or columns) we have a shape of (1x40) this means we will start with an input shape of 40.
The first two layers will have 256 nodes. The activation function we will be using for our first 2 layers is the ReLU(Rectified Linear Activation). This activation function has been proven to work well in neural networks.
We will also apply a Dropout value of 20% on our first two layers. This will randomly exclude nodes from each update cycle which in turn results in a network that is capable of better generalisation and is less likely to overfit the training data.
Our output layer will have 10 nodes (number of labels) which matches the number of possible classifications. The activation is for our output layer is softmax. Softmax makes the output sum up to 1 so the output can be interpreted as probabilities. The model will then make its prediction based on which option has the highest probability.


