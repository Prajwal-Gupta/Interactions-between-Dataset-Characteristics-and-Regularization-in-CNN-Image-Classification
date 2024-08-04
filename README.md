# Interactions-between-Dataset-Characteristics-and-Regularization-in-CNN-Image-Classification

Regularization is essential to increasing the accuracy of convolutional neural networks and regularization methods are frequently employed in the task of image classification. \\
Our project aims to determine the effect of regularization methods Cutout, RandomErasing, Dropout, Max Dropout, and Label Smoothing on two datasets of varying spatial features, number of categories, as well as degrees of categorical distinction. \\
To do this we employed two CNN architectures: ResNet and AlexNet. The datasets we used were CIFAR-10 (low spatial features, multiclass classification, high categorical distinction), and CelebA (high spatial features, binary classification, low categorical distinction). Through methodical trials of each combination of regularization methods, CNN, and dataset, we identified RandomErasing and Label Smoothing as the best set of regularization methods for CIFAR-10 on ResNet CNN, with test accuracy of 87.22%, and RandomErasing alone as the best for CelebA with test accuracy of 97.46%. For AlexNet CNN, we identified Cutout as the best regularization methods for CIFAR-10, with test accuracy of 81.64%, and Cutout with RandomErasing as the best for CelebA with a test accuracy of 97.86%.\\
\\
Our research project delves into unraveling the intricacies of image content and classification categories under the influence of diverse regularization methods and CNN algorithms. Through this exploration, we aim to gain a nuanced understanding of how these factors interact and shape the outcomes in image processing. Our collective effort is to distinguish this research by focusing on the unique interplay between regularization techniques, CNN algorithms, and image content. By shedding light on these dynamics, we anticipate contributing valuable insights to refine and optimize CNN models, advancing the realm of computer vision and image classification. \\
\\
## Methods
In the design of our methods, we had three main considerations. First was the datasets to use. We wanted to find datasets with varying characteristics (level of categorical distinction, image complexity, and number of spatial features) as to clearly show the interaction between these characteristics and our regularization methods. Following from this, naturally, was to determine which regularization methods to include. We wanted to include regularization methods in each of the three main areas: data augmentation, internal structure changes, and label augmentation. Lastly, we wanted to run our experiments on multiple CNN architectures to account for model (non-data) related differences.\\

### Datasets
After considering a number of datasets we ended up using two popular existing datasets: CIFAR-10 and CelebA.\\
CIFAR-10 is one of the most popular datasets used in multiclass image classification. It is a subset of the Tiny Images dataset with 60000 images for each of 10 classes. The classes in this dataset are highly distinct including various classes of vehicles and animals. The images are 32x32 and have relatively few spatial features.  \\
CelebA is a human face image dataset containing 202,599 images of 10,177 celebrities. The dataset has 40 (non-mutually exclusive) binary labels. We chose one of these labels, male vs female, to focus on. The classification done here is much less distinct. While airplanes and deer are highly differentiated in visual attributes, labels of male and female can be much more ambiguous. Additionally, the images in this dataset are size 178×218 and thus have a relatively higher number of spatial features. \\

### CNN Architectures
While not central to our primary hypothesis, the choice of CNN architectures was crucial due to their potential impact on our results. We employed two architectures: ResNet\cite{ResNet} and AlexNet\cite{AlexNet}. ResNet supports deeper network structures with its skip connections, mitigating vanishing gradient issues and reducing overfitting risks. In contrast, AlexNet, chosen for its simpler structure, offered a balance between training efficiency and accuracy maintenance. This architecture facilitated a more efficient training process without significant accuracy losses, optimizing the trade-off between training duration and performance. Additionally, the shallow network design of AlexNet simplified the analysis of training enhancements, contributing to overall efficiency and effectiveness. \\
AlexNet is used in 2 configurations for an in-depth exploration: 
- The network with all the regularizations accurately that included dropout and Batch Normalization.
- The network with a bare-bone CNN inspired by the AlexNet architecture.

### Regularization Methods
Our main goal in the selection of regularization methods was to cover all three main categories of regularization (data augmentation, internal structure changes, and label augmentation) as well as to include methods that are currently popular for use in Image classification. By achieving these two goals, we can achieve the most representative and applicable results. The regularization methods we employed are (by category):
- Data Augmentation: Cutout, RandomErasing
- Internal Structure Changes: Dropout, MaxDropout 
- Label Augmentation: Label Smoothing


