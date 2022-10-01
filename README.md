# Effects of Quantizing pre-trained Deep Learning Model using Tensorflow

## Desciption

## Results

#### Rsenet50

|  | Original Model | Dynamic Range Optimization | Float16 Optimization | Int8 Optimization |
| :---: |  :---: |  :---: |  :---: | :---: |
| Time to Quantize in mins | - | | | 1.59 |
| Size in Mb | 103.1 | 26 | 51.1 | 26.3 |
| Accuracy | 83% | 83% | 83 % | |
| Inference time | 72.9 ms | 33.23 ms | 54.8 ms | |

#### VGG16

|  | Original Model | Dynamic Range Optimization | Float16 Optimization | Int8 Optimization |
| :---: |  :---: |  :---: |  :---: | :---: |
| Time to Quantize | - | | | 3.49 |
| Size in Mb | 553.5 | 138.5 | 276.5 | 138.5 |
| Accuracy | 75.79% | 75.97 % | 75.79 % | |
| Inference time | 109.6 ms | 101.7 ms | 147.54 ms | |

#### MobileNet_v2

|  | Original Model | Dynamic Range Optimization | Float16 Optimization | Int8 Optimization |
| :---: |  :---: |  :---: |  :---: | :---: |
| Time to Quantize | - | | | 1.1 |
| Size in Mb | 14.6 | 3.8 | 7 | 4 |
| Accuracy | 6.59 % | 6.24 % | 6.59 % | |
| Inference time | 36.4 ms | 9.1 ms | 13.55 ms | |
