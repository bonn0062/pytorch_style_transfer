# pytorch_style_transfer

# Style Transfer with Deep Neural Networks 
#### Adapted from the Udacity Facebook AI PyTorch Scholarship Challenge


In this notebook, we recreate a style transfer method that is outlined in the paper, [Image Style Transfer Using Convolutional Neural Networks, by Gatys](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) using PyTorch.

In this paper, the features used in this style transfer are found in the 19-layer VGG Network, which is comprised of a series of convolutional and pooling layers, and a few fully-connected layers. In the image below, the convolutional layers are named by stack and their order in the stack. Conv_1_1 is the first convolutional layer that an image is passed through, in the first stack. Conv_2_1 is the first convolutional layer in the *second* stack. The deepest convolutional layer in the network is conv_5_4.

Style transfer relies on separating the content and style of an image. Given one content image and one style image, we aim to create a new, _target_ image which should contain our desired content and style components:
* objects and their arrangement are similar to that of the **content image**
* style, colors, and textures are similar to that of the **style image**


We use a pre-trained VGG19 Net to extract content or style features from a passed in image, then formalize the idea of content and style _losses_ and use those to iteratively update our target image until we get a result that we want.
