# Computer Vision(CV) in Deep Learning

## CONTENT

- [BACKGROUND](#BACKGROUND)
- [RELATED WORKS](#RELATEDWORKS)
- [SOLUTIONS](#SOLUTIONS)
- [IMPLEMENT NOTE](#IMPLEMENT)

## BACKGROUND
Explore some novel methodology with higher performance and rubustness for ***AOI Fault Detection*** & ***Vision-based Servo Control***.

The *inspection* and *classification* of defects in *printed circuit board (PCB)* is crucial for electronic production manufacturers. cause yield rate is the key to profitability for manufacturers, especially in the process of integrated circuit. In order to improve quality engineering yield and execution efficiency, *automated optical inspection (AOI)* equipment is used to detect the types and causes of defects.

The main function if AOI is detection of defect fields and segmentation, so in 2019 the HRIPCB dataset is proposed,it containing 1386 images and 6 types of defects, for the evaluation of various problems on such classification, detection and semantic tasks.

##### *Download [HRIPCB dataset](https://www.kaggle.com/datasets/akhatova/pcb-defects) on Kaggle.*([paper link](https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/joe.2019.1183))

## RELATED WORKS
Google's [*"Attention is all you need"*](https://arxiv.org/abs/1706.03762) published in 2017 kicked open the door to the world of AI. In the past, neural networks (such as CNNs and RNNs) were modeled based on certain artificially given assumptions, such as locality and translation invariance in convolutional operations, but these assumptions also made NLP tasks unsuccessful after all. Therefore, a new type of Transformer network has been proposed that enables neural networks to perceive both spatial and temporal information by combining Positional-Encoding and Self-Attention mechanisms to facilitate the processing of cross-domain data types.

##### *More materials about Transformers stored in repository* [`/MarkovChen/NLP`]()

- **Vision Transformer, ViT**
Since the success of AlexNet at [ICCV](https://ieeexplore.ieee.org/xpl/conhome/1000149/all-proceedings) in 2012, convolutional neural networks have been a major technique in CV, and various innovative architectures based on convolutional operations, such as ResNet, VGG, ResNet, and U-Net, have emerged in full swing, but they all seem to face intractable dilemmas in terms of cross-domain scalability.<br>
To solve this problem, Google Research and Google Brain team directly applied the Transformer, which can handle spatio-temporal problems, to CV, and used each patch of the image as input to obtain **Image classification** performance comparable to CNN, called Vision Transformer (ViT)[[arxiv2010.11929]](https://arxiv.org/abs/2010.11929)/[[Github]](https://github.com/google-research/vision_transformer.git)。However, the locality and translation invariance in the sample need to be trained by the model, so **large datasets** (like ImageNet-21K) is required to show its excellent performance with less compulation cost and can perform transfer learning well after fine-tuning.<br>
<img src="https://i.imgur.com/xp83Jfl.png" width = "650"/><br>Here we clarify the reason why ViT transforms the image into many 16x16 patches? The main reason is that if the Transformer takes each pixel as input, the computational complexity is too high. for example, the sequence length of a 240x240 image is 57,600 dimensions. compared with the complexity of BERT 512 dimensions can be said to be destructive, so a picture will first be divided into several small patches before input.**(so we can control the complexity of the computation by changing the size of the patch)**

****
- **Shifted Window Transformer, Swin**
Developed by Micrsoft Research Asia in 2021, Swin improves on the shortcomings of the original ViT in **object recognition** and **semantic segmentation**[[arxiv2103.14030]](https://arxiv.org/abs/2103.14030). The main purpose of Swin is to enable the Transformer to consider the relationship between two neighboring patches through a Shifted Window, and to extract multi-scale features of object simultaneously, providing a general backbone for different applications of neural networks.<br>
Among them, Swin introduces a lot of prior knowledge that has been successful in CNNs in the past. the Swin operation shown in (a) takes reference from the U-Net method of extracting **multi-scale features** from each down-sampling layer and propagating forward jointly. it also applying self-attention mechanism to each patch to reduce computational complexity. In (b), **overlapping moving windows** are applied to enable Transformer considering the anterior-posterior correspondence information between each patch. Meanwhile, (d) also makes reference to the pooling operation of CNN in the connection between layers, and uses **merging** to pool the weighted features of neighboring patches.<br><img src="https://i.imgur.com/vqubjjM.png" width = "650"/>

##### The official implementation for "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows".

|*tasks*|`Image-Classification`|`Object-Detection`|`Semantic-Segmentation`|
| :---:|:---:|:---:|:---:| 
|   *code*   |[Github](https://github.com/microsoft/Swin-Transformer.git)|  [Github](https://github.com/SwinTransformer/Swin-Transformer-Object-Detection)   |[Github](https://github.com/SwinTransformer/Swin-Transformer-Semantic-Segmentation.git)| 
| *Environment*|PyTorch|PyTorch|PyTorch| 

## SOLUTIONS
- **TransGAN**
SwinTransformer Data Augmentation and Generation. [[arxiv2102.07074]](https://arxiv.org/abs/2102.07074)/[[Github]](https://github.com/VITA-Group/TransGAN.git).

##### *More materials about GAN stored in repository* [`MakovChen/Generative-Models`]()

<img src="https://i.imgur.com/yWxFzSC.jpg" width = "640"/>

****

- **Swin Transformer based Reinforcement Learning**
On-Policy.[[arxiv2206.15269]](https://arxiv.org/abs/2206.15269)



## IMPLEMENT NOTE
### Keras
* [SwinTransformer_CIFAR_100.ipynb]()

### Github
(not tried yet)
