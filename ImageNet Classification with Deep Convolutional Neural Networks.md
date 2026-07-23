The authors of the paper proposed an optimized model for image classification by entering the ILSVRC competition, relying on three main factors to win over their competitors:
1. A larger dataset
2. A larger model
3. Newly implemented regularization techniques 

The authors stuck with a convolutional neural network (CNN) as their primary model due to its efficiency. However, one caveat of using such a model was its high computational cost and time requirement, which they accommodated using a 2-GPU parallel system that significantly improved processing speed.

Their primary dataset was ImageNet, which contains 15 million images across 22,000 categories. Of course, they could not process all of them, so they managed this by keeping ~1,000 images across 1,000 categories.

The evaluation was categorized using top-1 and top-5 error rates. Each image was reshaped to 256x256 dimensions, where the center of the image was cropped to match the specific dimensions given previously. 

For regularization, the authors implemented a ReLU activation function and separated each convolution into two distinct upper and lower divisions, where each convolutional layer was native to its respective GPU. Although not strictly needed, the authors also implemented local response normalization and overlapping pooling, which improved generalization.

<img width="680" height="225" alt="image" src="https://github.com/user-attachments/assets/516e5c0b-7928-438e-84c7-90941bac5685" />


*The image showcases the 5 convolutional layers and 3 interconnected layers, with a softmax function at the end.*

To handle overfitting, they used data augmentation (where they manipulated each image into different variations) alongside dropout.

<img width="693" height="208" alt="image" src="https://github.com/user-attachments/assets/3436b98d-f157-4afe-9320-cbea2492c3dc" />


*The model's results.*

<img width="710" height="270" alt="image" src="https://github.com/user-attachments/assets/b7440541-598d-4e49-81b4-f38d7e022ebb" />
*Showcases that the kernels at the top are specialized for geometric features, while the bottom ones are specialized for color and discoloration.*

In summary, this model seemed to outperform traditional multilayer perceptrons when it comes to image classification.
