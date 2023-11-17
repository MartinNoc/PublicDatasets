# FLamby: Datasets and Benchmarks for Cross-Silo Federated Learning in Realistic Healthcare Settings

FLamby is a benchmark for cross-silo Federated Learning with natural partitioning, currently focused in healthcare applications. The FLamby package contains data loaders (handle data preprocesssing and partitions), evaluation of trained models, and benchmark code. It does not contain datasets, which have to be downloaded separately.

For model references and papers, see the FLamby paper, Table 1.

Links: [Paper](https://openreview.net/pdf?id=GgM5DiAb6A2), [Paper+Appendix](https://arxiv.org/pdf/2210.04620.pdf), [Github](https://github.com/owkin/FLamby)

## Camelyon16
|||
|--|--|
|Task|Breast and colon cancer detection|
|Datatype|images|
|Classes|2 (yes/no): tumor on slide|
|Samples|399 slides|
|Sample shape|10,000 x 2,048 after feature extraction|
|Sample notes|distributed across 2 sites<ul><li>243 (169 + 74 samples, train + test) @ Radboud University Medical Center<li>156 (101 + 55) @ University Medical Center Utrecht</ul>50 GB after feature extraction, 850 GB in total|
|Original Paper| [[16]](#16) |
|Links|[Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_camelyon16), [Datasheet](https://academic.oup.com/gigascience/article/7/6/giy065/5026175?login=true#117856577) |
|Model|DeepMIL [[1]](#1)<ul><li>Conv(1,20), ReLU, maxpool<li>Conv(20,50), ReLU, maxpool<li>Linear(800,500), ReLU<li>Linear(500,128), Tanh<li>Linear(128,1), Softmax|
|Notes|MIL (Multiple Instance Learning): Bag of features with individual lables, with a single label training per bag|

## TCGA-BRCA
The Cancer Genome Atlas ([TCGA](https://www.cancer.gov/ccg/research/genome-sequencing/tcga)) Breast Invasive Carcinoma (BRCA)
|||
|--|--|
|Task|Survival prediction|
|Datatype|tabular data|
|Output|concordance index|
|Samples|1,088 examples|
|Sample shape|39-attribute vector|
|Sample notes|distributed across 6 sites<ul><li>USA Northeast: 311 (248 + 63, train + test) <li>USA South: 196 (156 + 40) <li>USA West: 206 (164 + 42) <li>USA Midwest: 162 (129 + 33) <li>Europe: 162 (129 + 33) <li>Canada: 51 (40 + 11)</ul>118 KB<p>categorical variables are one-hot encoded|
|Original Paper|[[6]](#6)|
|Links|[Dataset](https://portal.gdc.cancer.gov/projects/TCGA-BRCA), [Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_tcga_brca) |
|Model|Cox Model [[8]](#8)<p>proportional hazards model: $\lambda(t,x_i)=\lambda_0(t)\exp\left(\beta^Tx_i\right)$|
|Notes|data produced by [[6]](#6) as base, further preprocessing like [[7]](#7)|

## ISIC2019
from the ISIC2019 challenge and the HAM1000 database.
|||
|--|--|
|Task|Skin lesion (melanoma) classification|
|Datatype|images|
|Classes|8: Melanoma, Melanocytic nevus, Basal cell carcinoma, Actinic keratosis, Benign keratosis, Dermatofibroma, Vascular lesion and Squamous cell carcinoma|
|Samples|23,247 samples|
|Sample shape|200 x 200 x 3 (RGB images)|
|Sample notes|distributed across 6 sites<ul><li>12,413 (9,930 + 2,483, train + test) @ Hospital Clinic de Barcelona<li>3,954 (3,163 + 791) @ MedUni Vienna (MoleMax HD)<li>3,363 (2,691 + 672) @ MedUni Vienna (DermLite FOTO) <li>2,259 (1,807 + 452) @ skin cancer practice of Cliff Rosendahl <li>819 (655 + 164) @ Memorial Sloan Kettering Cancer Center <li>439 (351 + 88) @ MedUni Vienna (Heine Dermaphot)</ul><p>6 GB|
|Original Paper| [[13]](#13) [[14]](#14) [[15]](#15)
|Links|[ISIC2019 challenge](https://challenge.isic-archive.com/landing/2019/), [HAM1000 database](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T), [Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_isic2019) |
|Model|EfficientNet [[12]](#12) B0 - B7<ul><li>B0: CNN with MBConv layer (similar to ResNet layers but with wider layers in between), total of 18 layers</ul>|
|Notes|Original dataset has 25,331 samples, FLamby keeps data where datacenter is known.|

## Heart-Disease
|||
|--|--|
|Task|Binary classification of the presence of heart disease|
|Datatype|tabular data|
|Classes|2 (yes/no): presence of heart disease|
|Samples|740 examples after preprocessing|
|Sample shape|13-attribute array (tabular data)|
|Sample notes|distributed across 4 sites:<ul><li>303 (199 + 104, train + test) @ Cleveland's Hospital <li>261 (172 + 89) @ Hungarian Hospital <li>46 (30 + 16) @ Switzerland Hospital <li>130 (85 + 45) @ Long Beach Hospital</ul>40 KB|
|Original Paper|[[20]](#20)|
|Links|[Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_heart_disease)|
|Model|Logistic Regression: linear + sigmoid|
|Notes|collected in 1988|

## LIDC-IDRI
Part of The Cancer Imaging Archive ([TCIA](https://imaging.cancer.gov/informatics/cancer_imaging_archive.htm))
|||
|--|--|
|Task|3D segmentation of lung CT scans|
|Datatype|3D CT scans|
|Output|Segmentation map|
|Samples|1,018 examples from 1010 patients|
|Sample shape|128 x 128 x 128 (3D CT scans)|
|Sample notes|distributed across 4 sites<ul><li>661 (530 + 131, train + test, 7 diff. GE Medical Systems LightSpeed)<li>74 (59 + 15, 4 diff. Philips Brilliance)<li>205 (164 + 41, five diff. Siemens Definition, Emotion, and Sensation)<li>69 (55 + 14, Toshiba Aquilion)</ul>115 GB|
|Original Paper|[[17]](#17)|
|Links|[Dataset](https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI#1966254a2b592e6fba14f949f6e23bb1b7804cc), [Paper](https://aapm.onlinelibrary.wiley.com/doi/10.1118/1.3528204), [Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_lidc_idri) |
|Model|VNet [[2]](#2) [[3]](#3)|
|Notes||

## IXI (Information eXtraction from Images)
Task: 3D segmentation of brain MRI images
Datatype: 3D MRI images
### Standard IXI
|||
|--|--|
|Samples|"nearly 600 MR images from normal, healthy subjects"|
|Sample shape|256 x 256 x 140|
|Sample notes|"T1, T2 and PD-weighted images, MRA images and Diffusion-weighted images (15 directions)" from 3 hospitals in London<ul><li>Hammersmith Hospital using Philips 3T<li>Guy's Hospital using Philips 1.5T<li>Institute of Psychiatry using GE 1.5T</ul>27 GB|
|Links|[Dataset](https://brain-development.org/ixi-dataset/), [Dataset TorchIO](https://torchio.readthedocs.io/datasets.html#id1)
### IXI Tiny
|||
|--|--|
|Samples|566 T1-weighted examples|
|Sample shape|83 x 44 x 55 (Flamby says 48 x 60 x 48)|
|Output|Segmentation map of shape 2 x 48 x 60 x 48|
|Sample notes|distributed across 3 hospital<ul><li>Hammersmith: 181 (145 + 36, train + test) <li>Guy's: 311 (249 + 62) <li>IOP: 74 (59 + 15)</ul>444 MB|
|Original paper| [[18]](#18)|
|Links|[Dataset TorchIO](https://torchio.readthedocs.io/datasets.html#ixitiny), [Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_ixi) |
|Model|3D UNet approximately 18 - 20 convolutions [[4]](#4) [[5]](#5)|
|Notes||

## KiTS2019
from the Kidney Tumor Segmentation Challenge 2019
|||
|--|--|
|Task|3D segmentation of kidney and tumor in CT scans|
|Datatype|3D CT scans|
|Output|Segmentation map: 0: background, 1: kidney, 2: tumor|
|Samples|96 examples|
|Sample shape|64 x 192 x 192|
|Sample notes|distributed across 6 sites: 12, 14, 12, 12, 16, 30|
|Original Paper|[[19]](#19)|
|Links|[KiTS Github](https://github.com/neheller/kits19), [Github](https://github.com/owkin/FLamby/tree/main/flamby/datasets/fed_kits19), Papers [[10]](#10) [[11]](#11), [KiTS19 Challenge](https://kits19.grand-challenge.org/data/) |
|Model|nnU-Net [[9]](#9)|
|Notes|Original dataset: 210 scans with segmentation mask, 90 without. FLamby only uses scans from sites with 10+ scans, resulting in 96 samples.|

## References
<a id="1">[1]</a> 
Maximilian Ilse, Jakub M. Tomczak, and Max Welling. Attention-based deep multiple
instance learning. https://github.com/AMLab-Amsterdam/AttentionDeepMIL. 2022.

<a id="2">[2]</a>
Fausto Milletari, Nassir Navab, and Seyed-Ahmad Ahmadi. V-net: Fully convolutional neural networks for volumetric medical image segmentation. In 2016 fourth international conference on 3D vision (3DV), pages 565–571. IEEE, 2016.

<a id="3">[3]</a>
Adaloglou Nikolaos. Deep learning in medical image analysis: a comparative analysis of multi-modal brain-mri segmentation with 3d deep neural networks. Master’s thesis, University of Patras, 2019. https://github.com/black0017/MedicalZooPytorch

<a id="4">[4]</a>
Olaf Ronneberger, Philipp Fischer, and Thomas Brox. U-net: Convolutional networks for biomedical image segmentation. In Medical Image Computing and Computer-Assisted Intervention–MICCAI 2015: 18th International Conference, Munich, Germany, October 5-9, 2015, Proceedings, Part III 18, pages 234–241. Springer, 2015.

<a id="5">[5]</a>
Özgün Çiçek, Ahmed Abdulkadir, Soeren S Lienkamp, Thomas Brox, and Olaf Ronneberger. 3d U-Net: Learning dense volumetric segmentation from sparse annotation. In International Conference on medical image computing and computer-assisted intervention, pages 424–432. Springer, 2016

<a id="6">[6]</a>
Liu J, Lichtenberg T, Hoadley KA, Poisson LM, Lazar AJ, Cherniack AD, Kovatich AJ, Benz CC, Levine DA, Lee AV, Omberg L, Wolf DM, Shriver CD, Thorsson V; Cancer Genome Atlas Research Network, Hu H. An Integrated TCGA Pan-Cancer Clinical Data Resource to Drive High-Quality Survival Outcome Analytics. Cell. 2018 Apr 5;173(2):400-416.e11. doi: 10.1016/j.cell.2018.02.052. PMID: 29625055; PMCID: PMC6066282.

<a id="7">[7]</a>
Andreux, M., Manoel, A., Menuet, R., Saillard, C., and Simpson, C., “Federated Survival Analysis with Discrete-Time Cox Models”, arXiv e-prints, 2020.

<a id="8">[8]</a>
David R Cox. Regression models and life-tables. Journal of the Royal Statistical Society: Series B (Methodological), 34(2):187–202, 1972

<a id="9">[9]</a>
Fabian Isensee, Paul F Jaeger, Simon AA Kohl, Jens Petersen, and Klaus H Maier-Hein. nnu-net: a self-configuring method for deep learning-based biomedical image segmentation. Nature methods, 18(2):203–211, 2021.

<a id="10">[10]</a>
Nicholas Heller, Fabian Isensee, Klaus H Maier-Hein, Xiaoshuai Hou, Chunmei Xie, Fengyi Li, Yang Nan, Guangrui Mu, Zhiyong Lin, Miofei Han, et al. The state of the art in kidney and kidney tumor segmentation in contrast-enhanced ct imaging: Results of the kits19 challenge. Medical Image Analysis, page 101821, 2020

<a id="11">[11]</a>
Nicholas Heller, Niranjan Sathianathen, Arveen Kalapara, Edward Walczak, Keenan Moore, Heather Kaluzniak, Joel Rosenberg, Paul Blake, Zachary Rengel, Makinna Oestreich, et al. The kits19 challenge data: 300 kidney tumor cases with clinical context, ct semantic segmentations, and surgical outcomes. arXiv preprint arXiv:1904.00445, 2019

<a id="12">[12]</a>
Mingxing Tan and Quoc Le. Efficientnet: Rethinking model scaling for convolutional neural networks. In International conference on machine learning, pages 6105–6114. PMLR, 2019.

<a id="13">[13]</a>
Philipp Tschandl, Cliff Rosendahl, and Harald Kittler. The HAM10000 dataset, a large collection of multi-source dermatoscopic images of common pigmented skin lesions. Scientific data, 5(1):1–9, 2018

<a id="14">[14]</a>
Noel CF Codella, David Gutman, M Emre Celebi, Brian Helba, Michael A Marchetti, Stephen W Dusza, Aadi Kalloo, Konstantinos Liopyris, Nabin Mishra, Harald Kittler, et al. Skin lesion analysis toward melanoma detection: A challenge at the 2017 international symposium on biomedical imaging (ISBI), hosted by the international skin imaging collaboration (ISIC). In 2018 IEEE 15th international symposium on biomedical imaging (ISBI 2018), pages 168–172. IEEE, 2018.

<a id="15">[15]</a>
Marc Combalia, Noel CF Codella, Veronica Rotemberg, Brian Helba, Veronica Vilaplana, Ofer Reiter, Cristina Carrera, Alicia Barreiro, Allan C Halpern, Susana Puig, et al. Bcn20000: Dermoscopic lesions in the wild. arXiv preprint arXiv:1908.02288, 2019.

<a id="16">[16]</a>
Geert Litjens, Peter Bandi, Babak Ehteshami Bejnordi, Oscar Geessink, Maschenka Balkenhol, Peter Bult, Altuna Halilovic, Meyke Hermsen, Rob van de Loo, Rob Vogels, et al. 1399 H&E-stained sentinel lymph node sections of breast cancer patients: the CAMELYON dataset. GigaScience, 7(6):giy065, 2018.

<a id="17">[17]</a>
Samuel G Armato III, Geoffrey McLennan, Luc Bidaut, Michael F McNitt-Gray, Charles R Meyer, Anthony P Reeves, Binsheng Zhao, Denise R Aberle, Claudia I Henschke, Eric A Hoffman, et al. The lung image database consortium (LIDC) and image database resource initiative (IDRI): a completed reference database of lung nodules on ct scans. Medical physics, 38(2):915–931, 2011.

<a id="18">[18]</a>
Fernando Pérez-García, Rachel Sparks, and Sebastien Ourselin. Torchio: a python library for efficient loading, preprocessing, augmentation and patch-based sampling of medical images in deep learning. Computer Methods and Programs in Biomedicine, 208:106236, 2021.

<a id="19">[19]</a>
Nicholas Heller, Niranjan Sathianathen, Arveen Kalapara, Edward Walczak, Keenan Moore, Heather Kaluzniak, Joel Rosenberg, Paul Blake, Zachary Rengel, Makinna Oestreich, et al. The kits19 challenge data: 300 kidney tumor cases with clinical context, ct semantic segmentations, and surgical outcomes. arXiv preprint arXiv:1904.00445, 2019.

<a id="20">[20]</a>
Andras Janosi, William Steinbrunn, Matthias Pfisterer, and Robert Detrano. Heart disease data set, 1988.