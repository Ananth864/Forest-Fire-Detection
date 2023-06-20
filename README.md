# Forest-Fire-Detection

### Objective 
To develop a robust deep learning algorithm for the Classification of forest
fires on the FLAME dataset:

### Dataset
This link provides FLAME (Fire Luminosity Airborne-based Machine learning Evaluation) dataset using drones during a prescribed pile burn in Northern Arizona, USA. 
https://ieee-dataport.org/open-access/flame-dataset-aerial-imagery-pile-burn-detection-using-drones-uavs

### Dataset Images

![Dataset](https://github.com/Ananth864/Forest-Fire-Detection/assets/85446106/d052931b-2a64-4198-b195-852d9edf690b)

## Aproach 
### Dataset Resizing
These application of the detection model will usually be on drones, hence it is necessary to use a lightweight model that achieves accurate predictions as fast as possible. Therefore it is important to resize the dataset to a size of 254x254 which will require a smaller model to predict. 

### Detection model
The size of the input layer depends on the image size and the number of channels
which in our case is (254 × 254 × 3). Then the value of RGBs in different channels are
scaled to a float number between -1.0 and 1.0. After that, we augment the data so we
get some randomly generated images which increases the dataset size. I am using
random shift and random rotation for the augmentation part here.
Below is the block diagram for the classification model I have proposed.

![finalmodel drawio (1)](https://github.com/Ananth864/Forest-Fire-Detection/assets/85446106/4b52294e-557e-4dca-929e-1b5d76f67db1)





