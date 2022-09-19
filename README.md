# EuroSAT-satellite-image-classification
EuroSAT: Land Use and Land Cover Classification with Sentinel-2

### Short Description

Goal: land use and land cover classification using Sentinel-2 multi spectral satellite images. The Sentinel-2 satellite images are openly and freely accessible provided in the Earth observation program Copernicus. I use the dataset of Patrick Helber, Benjamin Bischke, Andreas Dengel and Damian Borth (reference papers below) which is based on Sentinel-2 satellite images covering 13 spectral bands (Level-1C) and consisting out of 10 classes with in total 27,000 labeled and geo-referenced images. 
I use a Convolutional Neural Network (CNNs) and achieve an accuracy of around 95\% for Level-1C data (same features as training data) and around 60% for level-2A data (less features than training data). 

### Project Details
Initial preparation: 
- Data Cleaning and Preprocessing, incl. standardization
- Data Augmentation, incl. random rotation, flipping and patch removals

Final Network Architecture:
- 3 Convolutional layer (32, 64, 128), followed by 3 fully connected layer (2048, 2048, 10) 
- Max pooling after each convolutional layer
- Kernel size: 5x5 (stride 1, padding 2)
- Loss: negative log-likelihood
- Optimizer: SGD
- Activation function: ReLu (last layer: Softmax)
- Number of model parameters to optimize: 21,262,730


References:
[1] Eurosat: A novel dataset and deep learning benchmark for land use and land cover classification. Patrick Helber, Benjamin Bischke, Andreas Dengel, Damian Borth. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, 2019.
[2] Introducing EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification. Patrick Helber, Benjamin Bischke, Andreas Dengel. 2018 IEEE International Geoscience and Remote Sensing Symposium, 2018.
