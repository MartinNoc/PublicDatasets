# ClinicalDatasets
Overview of public clinical datasets

|| Dataset | Input type | Task | Sample size |
|--|:---|:---|---|---|
|| [BreakHis](datasets/BreakHis.md)|images|binary classification|700 x 460 x 3||[Paper](https://ieeexplore.ieee.org/abstract/document/7312934)|
|[OpenML](datasets/OpenML.md)|<p>[dermatology](datasets/OpenML.md#dermatology)<p>[pbcseq](datasets/OpenML.md#pbcseq)|tabular data|classification|<p>1 x 34<p>1 x 19||<p>[Webpage](https://www.openml.org/search?type=data&status=active&id=35&sort=runs)<p>[Webpage](https://www.openml.org/search?type=data&status=active&id=516&sort=runs)|
|[FLamby](datasets/FLamby.md)|<p>[Camelyon16](datasets/FLamby.md#camelyon16) <p>[TCGA-BRCA](datasets/FLamby.md#tcga-brca) <p>[ISIC2019](datasets/FLamby.md#isic2019) <p>[Heart-Disease](datasets/FLamby.md#heart-disease) <p>[LIDC-IDRI](datasets/FLamby.md#lidc-idri) <p>[IXI Tiny](datasets/FLamby.md#ixi-information-extraction-from-images) <p>[KiTS2019](datasets/FLamby.md#kits2019)|<p>images <p>tabular data <p>images <p>tabular data <p>3D CT scans <p>3D MRI images <p>3D CT scans|<p>cancer detection <p>survival prediction <p>melanoma classification <p>heart disease detection <p>segmentation <p>segmentation <p>segmentation|<p>10,000 x 2,048 <p>1 x 39 <p>200 x 200 x 3 <p>1 x 13 <p>128 x 128 x 128 <p>83 x 44 x 55 <p>64 x 192 x 192|<p>&check;<p>&check;<p>&check;<p>&check;<p>&check;<p>&check;<p>&check;|see individual notes|
|[FLOP](datasets/FLOP.md)|<p>[COVIDx](datasets/FLOP.md#covidx) <p>[Kvasir](datasets/FLOP.md#kvasir)|<p>images <p>images|<p>classification <p>Gastrointestinal disease classification|<p>480 x 480 x 3 <p>from 720 x 576 up to 1920 x 1072|
||[RSNA Breast Cancer](datasets/RSNA-BCD.md)|images|breast cancer detection|from 2,776 x 2,082 to 3,328 x 2,560
||[MIMIC-III](datasets/MIMIC-III.md)|mixed (mostly tabular)|?||
||[NHANES](datasets/NHANES.md)|tabular data|?||


## Additional dataset information:

### Joshi et al.
Joshi et al. Federated Learning for Healthcare Domain - Pipeline, Applications and Challenges. 2022.

Tables 1 and 2 list studies on FL and ML in healthcare. Used datasets of these studies need to be investigated.

### UK Biobank
https://www.ukbiobank.ac.uk/

### PhysioNet
https://physionet.org/

The PhysioNet dataset is a collection of physiological signals and clinical data for use in research and education. It includes data on electrocardiograms (ECGs), electroencephalograms (EEGs), blood pressure, and other physiological signals.

### Global Health Observatory (GHO) data
https://www.who.int/data/gho

The GHO data from the World Health Organization (WHO) includes health-related statistics for countries around the world. The dataset includes information on mortality rates, disease incidence, health expenditures, and other health indicators.

## Todo
### Diabetes Dataset (1988)

This dataset contains data related to diabetes patients and includes information such as age, gender, body mass index, blood pressure, and various blood serum measurements.

[Kaggle dataset](https://www.kaggle.com/uciml/pima-indians-diabetes-database)

<ul><li>768 patients (females at least 21 years old of Pima Indian heritage)
<li>features: pregnancies, glucose, blood pressure, skin thickness, insulin, bmi, diabetes pedigree function, age
<li> 500 without diabetes, 268 with diabetes
</ul>

### TCGA-LUAD
The Cancer Genome Atlas Lung Adenocarcinoma Collection

https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=6881474

### OASIS
OASIS: Brain MRIs, 400+, 256 x 256

https://oasis-brains.org/

### ADNI
ADNI: Alzheimer's Disease Neuroimaging Initiative, MRI

https://adni.loni.usc.edu/

### NLST
Cancer Imaging Archive: 21M images (11 TB), only cancer images??

https://wiki.cancerimagingarchive.net/display/NLST/National+Lung+Screening+Trial

### Covid-19
chest x-ray (normal, pneumonia, covid), 100-200 per class

https://www.kaggle.com/datasets/pranavraikokte/covid19-image-dataset
