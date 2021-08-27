# StegAnalysis using CNN model (Theory)
in this project ,we will use StegAnalysis for classifying images dataset in two different groups (steg image/cover image),for Constructing StegAnalysis Using CNN model,and my initial projects is preparing, furthermore my intial documents will be preparing in further project.

Notice:i provide for you basic knowledge about my study in this filed,inspired by `MIT` Group,and i put `.pptx` file in my repo,i think it is very useful for your first step to study. moreover, I already use a paper about `An Improved CNN Steganalysis Architecture Based on “Catalyst Kernels” and Transfer Learning` in [link](https://link.springer.com/chapter/10.1007/978-3-319-97749-2_9) to prepare my implementation in `keras`.


## Dataset
in this project we use a `10000` image dataset from [link](http://agents.fel.cvut.cz/stegodata/) provided by `Jessica Fridrich` as a `BossBase V 1.01`. each image has a `.pgm` format  with size `128*128` as a `gray-level` image such as below `cover` image. furthermore, we use two steganography algorithm dataset `WOW, S-Uniward` with different `bpp` rates as a counterpart of cover data called `stego` images. Note that put `stego` and `cover` dataset in the four directories `dataset/train/stego`,`dataset/test/stego`,`dataset/train/cover` and `dataset/test/cover`  :

![image](https://user-images.githubusercontent.com/53394692/131145054-82f29047-0cbe-4bd0-b3b0-e62fb71e87d0.png)


## install anaconda, CUDA, cuDNN, Tensorflow
for using IDEs such as `Jupyter Notebook` and `Power Shell` to run commands (our code) in `.py` format and different python packages such as `numpy,....`,we install `anaconda` by helping this [link](https://www.anaconda.com/products/individual) in windows 10. since i used `GPU RTX 2080 Ti` for this project , you must install related `CUDA` and `cuDNN` basis on your GPU by these links [CUDA](https://developer.nvidia.com/cuda-downloads),[cuDNN](https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html). for installing `tensorflow` you must download required `.whl` files in [link](https://www.tensorflow.org/install/pip#package-location) adn install it by `python -m pip install <wheel_url>`.
(NOTICE : you must use your way in installing these mentioned packages and library, dont worry there are many videos in `youtube` and `google` for installing them.)

## QT Designer
for creating graphical user interface (gui), we use QT Designer to create an environment. you can download that on [link](https://www.qt.io/download) and install it easily. after installing, you will see the software environment such as below. you see different properties and options to make your gua :

![image](https://user-images.githubusercontent.com/53394692/131082858-e3d43e3f-f132-459b-bdc6-41ee718fbc4e.png)

and finally, i build these two guis for my purpose. the first gui used for `train` phase and another used for `test` phase :
|   train-gui        |      test-gui        |
|--------------------|----------------------|
|  ![train-gui](https://user-images.githubusercontent.com/53394692/131087974-2d43f2a8-2577-4f4c-8a54-9dc95e79fd66.png)  |   ![test-gui](https://user-images.githubusercontent.com/53394692/131087982-12271ff6-7f65-4623-ba96-ba3d2ffec653.png)    |

```
# details of properties in train-gui
Date : date of day (you train your model)
train_cover_path : the path of train cover data
test_cover_path : the path of validation cover data
train_stego_path : the path of train stego data
test_stego_path : the path of validation stego data
model_version : selecting your neural network version
epochs : number of training epochs
classes : number of classes (2 stego/cover)
batch_size : #number of batch_size 
output_path : path of epochs result (each 10 epochs)
train : starting train phase 
result : showing charts of training and validation
train time : showing the time of train phase
```
```
# details of properties in test-gui
Date : date of day (you train your model)
show result : train loss/acc and val loss/acc (in end epoch) will be shown
test image : the path of test image will be filled
test time : the time of testing phase will be shown
```
 
when you create the output file , `.ui`  files will be created. in our work, ther have two `.ui` files such as `train-gui` and `test-gui` . 

