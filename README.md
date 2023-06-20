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

<img src="https://github.com/Ananth864/Forest-Fire-Detection/assets/85446106/4b52294e-557e-4dca-929e-1b5d76f67db1" width="400" height="1000">

## Results
<img width="500" alt="image" src="https://github.com/Ananth864/Forest-Fire-Detection/assets/85446106/dfaed016-e333-474b-a9e4-d4a640b97cc7">
<img width="500" alt="image" src="https://github.com/Ananth864/Forest-Fire-Detection/assets/85446106/2eb6e480-7da2-4453-ad01-5ce135c4fc90">

The improvements in all the classification metrics we observed in our model is clearly
visible. The accuracy increased from 0.78 to 0.91. Similarly, a significant improvement
can be seen for other metrics like precision, recall, and f1-score too.




