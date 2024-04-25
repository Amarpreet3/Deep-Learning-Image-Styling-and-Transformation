![Python 2.7](https://img.shields.io/badge/python-2.7-green.svg)
![Python 3.5](https://img.shields.io/badge/python-3.5-green.svg)

# Image Styling and Transformation
Amarpreet Kaur (amarpreet.kaur@torontomu.ca) |  Toronto Metropolitan University


# Style transfer: 



![output_7_4](https://github.com/Amarpreet3/Deep-Learning-Image-Styling-and-Transformation/assets/96805692/62be244b-4777-4fa7-a7d1-c98999e7a417)


## Models and files
I applied BFA to the following model:
A pre-trained VGG-19 encoder (from input layer to **relu41** layer; fixed during training) and a blockwisely trained decoder which can reproduce the **relu31**, **relu21**, **relu11** features and the input image. The ZCA transformations are embedded at the bottleneck and the reproduced reluN1 layers in the decoder.
    - The model is in ```utils/model_relu.py``` and the associated checkpoint is in ```ckpts/ckpts-relu```.
    - A demo that uses this model to stylize example images in ```figures/``` is shown in ```relu_demo.py```. The resulting stylized images are in ```results/```.

Stylization with both models requires guided filtering in ```utils/photo_gif.py``` as the post-processing.



## Stylize images
To stylize a image put the content images in ```figures/content``` and the style images in ```figure/style``` then run ```relu_demo.py```

## Training
```train.py``` is the training code for our model. The usage is provided in the file.

## Requirements 
- tensorflow v2.0.0 or above (I developed the models with tf-v2.4.1 and I also tested them in tf-v2.0.0)
- Python 3.x
- keras 2.0.x
- scikit-image
  
### Tutorial

Please check out the [FastPhotoStyle Tutorial]((https://github.com/NVIDIA/FastPhotoStyle/blob/master/TUTORIAL.md)).
## Citation

**PhotoWCT2: Compact Autoencoder for Photorealistic Style Transfer Resulting from Blockwise Training and Skip Connections of High-Frequency Residuals** published in WACV 2022.

