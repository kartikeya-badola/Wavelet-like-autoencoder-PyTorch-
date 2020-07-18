# Wavelet-like-autoencoder-PyTorch-
A PyTorch Implementation of the base model of wavelet like Autoencoder
https://arxiv.org/pdf/1712.07493.pdf

Chen, T., Lin, L., Zuo, W., Luo, X. and Zhang, L., 2018, April. Learning a wavelet-like auto-encoder to accelerate deep neural networks. In Thirty-Second AAAI Conference on Artificial Intelligence.

Note that the architectural details are not the same as what is presented in the paper (or in their github repo where the model is implemented in Caffe). Batch Norm followed by Sigmoid usually works very well for image encoding applications hence I used it.

# Some results

Trained this model on Miccai Gleason 2019 dataset (https://bmiai.ubc.ca/research/miccai-automatic-prostate-gleason-grading-challenge-2019/gleason2019-data). The images were patched by a custom code and was sent through the Wavelet-Like Autoencoder. 

The original image was cropped to 4000x4000 size. Patches of 500x500 were taken and then downsampled to 224x224. The Wavelet-Like autoencoder prepare two images of half the size (112x112). One corresponds to low wavelet level and the other corresponds to higher wavelet level. Usually most of the information is contained in the lowest wavelet level whereas the higher wavelet level store information about the high frequency components of the image (eg. edges). Here is one image processed using this autoencoder:

