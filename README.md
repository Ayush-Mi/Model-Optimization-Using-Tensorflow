# Effects of Quantizing pre-trained Deep Learning Model using Tensorflow

This repo examines the effect of post training quantization on the performance of pretrained kera models using Tensorflow API.

## Desciption

Here we have taken three image classification model pretrained on Imagenet dataset from keras api and performed post training quantization using Tensorflow API. Resnet50, Vgg16 and Mobilenetv2 were examined for the change in accuracy, inference time, size of the model and the time it take to quantize them. The validation data from  was used to test. All the experiments were performed on Mac M1-pro 32gb.

For testing we have used the validation data from [Imagenette](https://github.com/fastai/imagenette) which has around 3900 images belonging to 10 classes from original imagenet data. All the experiments were performed on Mac M1 pro 32gb and the images were passed to the model with the batch size of 1.

## Dependencies

Downlaod [Imagenette](https://github.com/fastai/imagenette) and place it in `val/` folder whilw Quantized models will be stored in `./Models` folder. Below libraries are the minimum requirement:

- Python 3.5+
- Tensorflow 2.7+
- Numpy
- Tqdm

## Results

With the above setup, following observations were made:
- Dynamic range quantization reduces the model size to a quarter of the original
- Float16 quantization reduces the model size to half of the original
- Int8 quantization is almost equal to dynamic range quantization
- Mobilenet v2 pretrained on imagenet data showed poor performance throughout the evaluation
- Inference time for different quantization methods depended upon the model to be quantized 
- Int8 quantization requires a subset of original train data to adjust the weights of model while performing the quantization


#### Rsenet50

|  | Original Model | Dynamic Range Optimization | Float16 Optimization | Int8 Optimization |
| :---: |  :---: |  :---: |  :---: | :---: |
| Time to Quantize in secs. | - | 42.7| 40.2 | 62 |
| Size in Mb | 103.1 | 26 | 51.1 | 26.3 |
| Accuracy | 83% | 83% | 83 % | 48 %|
| Inference time | 72.9 ms | 33.23 ms | 54.8 ms | 83.3 ms |

#### VGG16

|  | Original Model | Dynamic Range Optimization | Float16 Optimization | Int8 Optimization |
| :---: |  :---: |  :---: |  :---: | :---: |
| Time to Quantize in secs | - | 129 | 117 | 153 |
| Size in Mb | 553.5 | 138.5 | 276.5 | 138.5 |
| Accuracy | 75.79% | 75.97 % | 75.79 % | 39.87 % |
| Inference time | 109.6 ms | 101.7 ms | 147.54 ms | 279.36 ms |

#### MobileNet_v2

|  | Original Model | Dynamic Range Optimization | Float16 Optimization | Int8 Optimization |
| :---: |  :---: |  :---: |  :---: | :---: |
| Time to Quantize in secs. | - | 34.7 | 34.1 | 42.2 |
| Size in Mb | 14.6 | 3.8 | 7 | 4 |
| Accuracy | 6.59 % | 6.24 % | 6.59 % | 3.16 % |
| Inference time | 36.4 ms | 9.1 ms | 13.55 ms | 13.99 ms|
