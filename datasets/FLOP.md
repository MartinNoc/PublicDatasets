# FLOP: Federated Learning on Medical Datasets using Partial Networks

Qian Yang, Jianyi Zhang, Weituo Hao, Gregory Spell, and Lawrence Carin. FLOP: Federated learning on medical datasets using partial networks. In KDD, 2021.

[Link to the Paper](https://dl.acm.org/doi/abs/10.1145/3447548.3467185)

[Github repo](https://github.com/jianyizhang123/FLOP) (includes dataset download instructions)

## COVIDx
Combines five publicly available Covid-19 data repositories
|||
|--|--|
|Task|Image multi-class classification of chest radiography images |
|Datatype|images|
|Classes|3: normal, pneumonia, Covid-19|
|Samples|15,533 (13,954 + 1,579, training + test) - ever updated|
|Sample shape|480 x 480 x 3|
|Sample notes|<p>training: 7,966 normal, 5,471 pneumonia, 517 Covid-19</p><p>test: 885 normal, 594 pneumonia, 100 Covid-19</p>|
|Links|Dataset: [Kaggle](https://www.kaggle.com/datasets/andyczhao/covidx-cxr2), [COVID-NET Github](https://github.com/lindawangg/COVID-Net)|
|Model|<p>COVID-NET [[1]](#1): CNN with 16 pepx modules à 5 Conv, 11.75M params - [Github](https://github.com/lindawangg/COVID-Net) <p>MobileNet-v2 [[4]](#4): 19 bottleneck layers à 3 Conv with ReLU, 3-4M params <p>ResNet50 [[5]](#5): 50 layers, 23M params <p>ResNeXt [[6]](#6): same shape of ResNet|
|Individual Datasets|<ul><li>COVID-19 Image Data Collection [[3]](#3) <li>COVID-19 Chest X-ray Dataset Initiative - [Github](https://github.com/agchung/Figure1-COVID-chestxray-dataset) <li>Actualmed COVID-19 Chest X-ray Dataset - [Github](https://github.com/agchung/Actualmed-COVID-chestxray-dataset) <li>COVID-19 radiography dataset - [Kaggle](https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database) <li>RSNA Pneumonia Detection Challenges dataset - [Kaggle](https://www.kaggle.com/c/rsna-pneumonia-detection-challenge/data)|

## Kvasir
|||
|--|--|
|Task|Gastrointestinal disease classification|
|Datatype|images|
|Classes|8: (Anatomical landmarks) Z-line, Pylorus, Cecum, (Phatological findings) Esophagitis, Polyps, Ulcerative colitis (Polyp Removal) Dyed and Lifted Polyps, Dyed Resection Margins|
|Samples|8,000 (1,000 per class)|
|Sample shape|from 720 x 576 up to 1920 x 1072|
|Sample notes|6,000 + 2,000 (training + test)|
|Original Paper|[[2]](#2)|
|Links|[Dataset](https://datasets.simula.no/kvasir/#data-collection), [Paper](https://dl.acm.org/do/10.1145/3193289/full/)|
|Model|<p>MobileNet-v2 [[4]](#4) <p>ResNet50 [[5]](#5)|

<a id="1">[1]</a>
Linda Wang and Alexander Wong. 2020. COVID-Net: A Tailored Deep Convolutional Neural Network Design for Detection of COVID-19 Cases from Chest X-Ray Images. arXiv preprint arXiv:2003.09871 (2020)

<a id="2">[2]</a>
Konstantin Pogorelov, Kristin Ranheim Randel, Carsten Griwodz, Sigrun Losada Eskeland, Thomas de Lange, Dag Johansen, Concetto Spampinato, Duc-Tien Dang-Nguyen, Mathias Lux, Peter Thelin Schmidt, et al. 2017. KVASIR: A multi-class image dataset for computer aided gastrointestinal disease detection. In 8th ACM on Multimedia Systems Conference. 164–169

<a id="3">[3]</a>
Joseph Paul Cohen, Paul Morrison, and Lan Dao. 2020. COVID-19 image data collection. arXiv 2003.11597 (2020). https://github.com/ieee8023/covid-chestxray-dataset

<a id="4">[4]</a>
Mark Sandler, Andrew Howard, Menglong Zhu, Andrey Zhmoginov, and Liang-Chieh Chen. 2018. Mobilenetv2: Inverted residuals and linear bottlenecks. In Proceedings of the IEEE conference on computer vision and pattern recognition. 4510–4520.

<a id="5">[5]</a>
Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun. 2016. Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition. 770–778.

<a id="6">[6]</a>
Saining Xie, Ross Girshick, Piotr Dollár, Zhuowen Tu, and Kaiming He. 2017. Aggregated residual transformations for deep neural networks. In Proceedings of the IEEE conference on computer vision and pattern recognition. 1492–1500.