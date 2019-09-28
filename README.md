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


