# EuroSAT-satellite-image-classification
EuroSAT: Land Use and Land Cover Classification with Sentinel-2

![EuroSAT overview image](https://github.com/Sesatt/EuroSAT-satellite-image-classification/blob/main/eurosat_overview_small.jpg?raw=true)

### Short Description

**Project goal**: land use and land cover classification using multi spectral Sentinel-2 satellite images.  
**Additional challenge**: training data was based on Level-1C data, while our classification set was based on Level-2A data (see definitions in appendix).  
**Dataset**: The Sentinel-2 satellite images are openly and freely accessible provided in the Earth observation program Copernicus. I use the dataset of Patrick Helber, Benjamin Bischke, Andreas Dengel and Damian Borth (reference papers in appendix) which is based on Sentinel-2 satellite images covering 13 spectral bands and consisting out of 10 classes with in total 27,000 labeled and geo-referenced images.  
**Result**: I use a Convolutional Neural Network (CNNs) and achieve an accuracy of around 95\% for Level-1C data (same features as training data) and around 60% for level-2A data (less features than training data). 

### Project Details

![Network Architecture](https://github.com/Sesatt/EuroSAT-satellite-image-classification/blob/main/Network_Architecture.jpg?raw=true)

**Data preparation**: 
- Data Cleaning and Preprocessing, incl. standardization
- Data Augmentation, incl. random rotation, flipping and patch removals

**Final Network Architecture**:
- 3 Convolutional layer (32, 64, 128), followed by 3 fully connected layer (2048, 2048, 10) 
- Max pooling after each convolutional layer
- Kernel size: 5x5 (stride 1, padding 2)
- Loss: negative log-likelihood
- Optimizer: SGD
- Activation function: ReLu (last layer: Softmax)
- Number of model parameters to optimize: 21,262,730


### Appendix

**Definitions**: ([source](https://sentinels.copernicus.eu/web/sentinel/technical-guides/sentinel-2-msi/products-algorithms)): 
- Level-1C product provides orthorectified Top-Of-Atmosphere (TOA) reflectance, with sub-pixel multispectral registration. Cloud and land/water masks are included in the product. 
- Level-2A product provides orthorectified Bottom-Of-Atmosphere (BOA) reflectance, with sub-pixel multispectral registration. A Scene Classification map (cloud, cloud shadows, vegetation, soils/deserts, water, snow, etc.) is included in the product.

**References**:
- Eurosat: A novel dataset and deep learning benchmark for land use and land cover classification. Patrick Helber, Benjamin Bischke, Andreas Dengel, Damian Borth. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, 2019.
- Introducing EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification. Patrick Helber, Benjamin Bischke, Andreas Dengel. 2018 IEEE International Geoscience and Remote Sensing Symposium, 2018.
