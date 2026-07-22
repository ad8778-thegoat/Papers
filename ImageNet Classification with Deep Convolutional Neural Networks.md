the authors of the paper proposed a optimized a model for image classificaiton, and propoosed so via entering the ILSVRC competition, and relied on 3 metrics to win over its competitiors:
  1.) Larges dataset
  2.) larger model
  3.) newly implemented regularization techniques 
the authors stuch with convulutes nueral network as their primary model due to its efficiencies, but with one caviat that came with using such model is its costs and time, so they accompinied it by a 2 GPU parrallel system which saved up on the processing speed portion of the data
Thier primary data set was ImageNet which contains 15 million images and 22k categories, but ofc they would not be able to process all of them, so they managed it by keeping ~1000 images over 1000+ categories.
The data was put into two catergories top-1 and top-5, and each image was reshaped into 246x246 dimentions and where the center of it was macked with the given specific dimentions given from before. 
For the regulization the authors implemented a ReLu activation model and also seprate each convulution into two distint upper and lower divisions, where each convolution layer is native to its own GPU it is in. And thought not needed the authours implemeneted normalization and overlapping pooling which improved generalization. 

<img width="680" height="225" alt="image" src="https://github.com/user-attachments/assets/516e5c0b-7928-438e-84c7-90941bac5685" />
# image showcases the 5 convulutions and 3 interconnected layes, wiht a softmax fuction at the end ^

to handle overfitting they used data augementation where they manupulate each image into different variations and also used dropout alongside
<img width="693" height="208" alt="image" src="https://github.com/user-attachments/assets/3436b98d-f157-4afe-9320-cbea2492c3dc" />
# The models Results ^

<img width="710" height="270" alt="image" src="https://github.com/user-attachments/assets/b7440541-598d-4e49-81b4-f38d7e022ebb" />
# Showcases the kernels of the top are specialized for geometrically and the bottom one for color discoloration

In summary this model seemed to outperform that of multilayer perceptron when it comes to image classification


