# Interactions-between-Dataset-Characteristics-and-Regularization-in-CNN-Image-Classification

-- REPO UNDER CONSTRUCTION -- <br>
<br>
Regularization is essential to increasing the accuracy of convolutional neural networks and regularization methods are frequently employed in the task of image classification. <br>
Our project aims to determine the effect of regularization methods Cutout, RandomErasing, Dropout, Max Dropout, and Label Smoothing on two datasets of varying spatial features, number of categories, and degrees of categorical distinction. <br>
To do this we employed two CNN architectures: ResNet and AlexNet. The datasets we used were CIFAR-10 (low spatial features, multiclass classification, high categorical distinction), and CelebA (high spatial features, binary classification, low categorical distinction). Through methodical trials of each combination of regularization methods, CNN, and dataset, we identified RandomErasing and Label Smoothing as the best set of regularization methods for CIFAR-10 on ResNet CNN, with test accuracy of 87.22%, and RandomErasing alone as the best for CelebA with test accuracy of 97.46%. For AlexNet CNN, we identified Cutout as the best regularization methods for CIFAR-10, with test accuracy of 81.64%, and Cutout with RandomErasing as the best for CelebA with a test accuracy of 97.86%. <br>
<br>

## Methods
### Datasets
After considering a number of datasets we ended up using two popular existing datasets: CIFAR-10 and CelebA. <br>
CIFAR-10 is one of the most popular datasets used in multiclass image classification. It is a subset of the Tiny Images dataset with 60000 images for each of 10 classes. The classes in this dataset are highly distinct including various classes of vehicles and animals. The images are 32x32 and have relatively few spatial features. <br>
CelebA is a human face image dataset containing 202,599 images of 10,177 celebrities. The dataset has 40 (non-mutually exclusive) binary labels. We chose one of these labels, male vs female, to focus on. The classification done here is much less distinct. While airplanes and deer are highly differentiated in visual attributes, labels of male and female can be much more ambiguous. Additionally, the images in this dataset are size 178×218 and thus have a relatively higher number of spatial features. <br>

### CNN Architectures
While not central to our primary hypothesis, the choice of CNN architectures was crucial due to their potential impact on our results. We employed two architectures: ResNet\cite{ResNet} and AlexNet\cite{AlexNet}. ResNet supports deeper network structures with its skip connections, mitigating vanishing gradient issues and reducing overfitting risks. In contrast, AlexNet, chosen for its simpler structure, offered a balance between training efficiency and accuracy maintenance. This architecture facilitated a more efficient training process without significant accuracy losses, optimizing the trade-off between training duration and performance. Additionally, the shallow network design of AlexNet simplified the analysis of training enhancements, contributing to overall efficiency and effectiveness. <br>
AlexNet is used in 2 configurations for an in-depth exploration: 
- The network with all the regularizations accurately that included dropout and Batch Normalization.
- The network with a bare-bone CNN inspired by the AlexNet architecture.

### Regularization Methods
Our main goal in the selection of regularization methods was to cover all three main categories of regularization (data augmentation, internal structure changes, and label augmentation) as well as to include methods that are currently popular for use in Image classification. By achieving these two goals, we can achieve the most representative and applicable results. The regularization methods we employed are (by category):
- Data Augmentation: Cutout, RandomErasing
- Internal Structure Changes: Dropout, MaxDropout 
- Label Augmentation: Label Smoothing


## Results

We obtained experiment results varying by dataset, CNN, and additional configurations. Broadly there were 4 experimental results run CIFAR-10 Results with ResNet, CelebA Results with ResNet, CIFAR-100 Results with ResNet, CIFAR-10 Results with AlexNet. 

Under each experiment we implemented different configurations using CUTOUT, ERASING, DROPOUT, MAXDROP and SMOOTHING. Following are the results for each experiment.

### CIFAR-10 Results with ResNet: 

We ran the CIFAR-10 dataset on our ResNet CNN with depth of 44.

<img width="390" alt="image" src="https://github.com/user-attachments/assets/4584ae54-fb78-4ce1-9134-fb64de5632f2">

<br>

<img width="390" alt="image" src="https://github.com/user-attachments/assets/054baa4e-319e-4e2a-a1dd-d2d85d2f2fe2">
<img width="390" alt="image" src="https://github.com/user-attachments/assets/16d77515-e379-49c7-84b3-570b381f8341">

### CelebA Results with ResNet:

Similarly the same experiments were run on the CelebA dataset. <br>
<img width="390" alt="image" src="https://github.com/user-attachments/assets/67e7ded4-9a77-4a3e-8c57-adb07ad8672b">

<br>

<img width="390" alt="image" src="https://github.com/user-attachments/assets/bf624aa1-e062-4f6e-80a8-2682bca5c4e9">
<img width="390" alt="image" src="https://github.com/user-attachments/assets/b0462487-fd32-4800-aa63-0379cb03ad7e">

### CIFAR-10 Results with AlexNet:

Now on CIFAR-10 we ran these following experiments with the following configurations.

<img width="390" alt="image" src="https://github.com/user-attachments/assets/530a5b43-d8f5-4c30-9964-2d5e3d0e22df">

<br>

<img width="390" alt="image" src="https://github.com/user-attachments/assets/26c31560-f4a3-4af9-bb9f-98ddf974bd20"> 
<img width="390" alt="image" src="https://github.com/user-attachments/assets/6a9c72f6-750a-49d5-b373-70bfd82bb394">

<br>

Here we can see the test accuracies of these configuraitons and see which regularization method worked the best.

<img width="390" alt="image" src="https://github.com/user-attachments/assets/a232e3b0-5d9e-41cb-9523-3d8d22d65bcb">


### CelebA Results with AlexNet: 

Similarly these were the experiments run for the CelebA dataset

<img width="390" alt="image" src="https://github.com/user-attachments/assets/94c16049-d011-49b8-9802-1534f9911c35">

<br>

<img width="390" alt="image" src="https://github.com/user-attachments/assets/3d17acab-9666-4039-9481-3d5c342f848f"> 
<img width="390" alt="image" src="https://github.com/user-attachments/assets/88cae29d-7534-4193-aafc-d7fa13374394">

<br>

Here we can see the test accuracies of these configuraitons and see which regularization method worked the best.

<img width="390" alt="image" src="https://github.com/user-attachments/assets/c8f2aedd-a922-4a87-ad2f-0c23df4a4c53">








