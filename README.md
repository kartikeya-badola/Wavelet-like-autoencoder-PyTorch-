# Wavelet-like-autoencoder-PyTorch-
A PyTorch Implementation of the base model of wavelet like Autoencoder
https://arxiv.org/pdf/1712.07493.pdf

Chen, T., Lin, L., Zuo, W., Luo, X. and Zhang, L., 2018, April. Learning a wavelet-like auto-encoder to accelerate deep neural networks. In Thirty-Second AAAI Conference on Artificial Intelligence.

Note that the architectural details are not the same as what is presented in the paper (or in their github repo where the model is implemented in Caffe). Batch Norm followed by Sigmoid usually works very well for image encoding applications hence I used it.

# Some results

Trained this model on Miccai Gleason 2019 dataset (https://bmiai.ubc.ca/research/miccai-automatic-prostate-gleason-grading-challenge-2019/gleason2019-data). The images were patched by a custom code and was sent through the Wavelet-Like Autoencoder. 

The original image was cropped to 4000x4000 size. Patches of 500x500 were taken and then downsampled to 224x224. The Wavelet-Like autoencoder prepare two images of half the size (112x112). One corresponds to low wavelet level and the other corresponds to higher wavelet level. Usually most of the information is contained in the lower wavelet levels whereas the higher wavelet levels store information about the high frequency components of the image (eg. edges). Here is one image processed using this autoencoder:

![Original Image](https://github.com/kartikeya-badola/Wavelet-like-autoencoder-PyTorch-/blob/master/original%20image.png)

This is the original image

![Wavelet Level 1](https://github.com/kartikeya-badola/Wavelet-like-autoencoder-PyTorch-/blob/master/wavelet%20level%201.png)

This is the lower wavelet level encoding of the above image. Note how it is half the size of the image above (see axis)

![Wavelet Level 2](https://github.com/kartikeya-badola/Wavelet-like-autoencoder-PyTorch-/blob/master/wavelet%20level%202.png)

This is the higher wavelet level encoding of the original image and basically stores structural information and high frequency components (such as edges)

![Reconstruction](https://github.com/kartikeya-badola/Wavelet-like-autoencoder-PyTorch-/blob/master/reconstruction.png)

This is the final reconstruction using the two encodings generated
