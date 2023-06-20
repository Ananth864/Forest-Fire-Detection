# Forest-Fire-Detection

### Objective 
To develop a robust deep learning algorithm for the Classification of forest
fires on the FLAME dataset

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

# Forest-Fire-Segmentation

### Objective 
To develop a robust deep learning algorithm for the Early Detection of
forest fires through drone images:

## Aproach 
### Dataset Resizing
These application of the segmentation model will usually be on drones, hence it is necessary to use a lightweight model that achieves accurate segmentations as fast as possible. Therefore it is important to resize the dataset to a size of 512x512 which will require a smaller model to predict. 

### Detection model
The model we proposed is based on the principles of attention squeeze architecture that
only require a few model parameters and U-Net with attention mechanism that could
highlight regions-of-interest (ROI) while suppressing irrelevant features could be
regarded as good candidates for real-time fire detection.

The attention gate guides the model's attention to important regions while suppressing
feature activation in unrelated areas. It substantially enhances the representational
power of the model without a significant increase in computing cost or number of
model parameters due to its lightweight design.

The addition of the initial Conv block of kernel size 1x1 is to reduce the number of
channels by letting the decide the new set of channels that is a linear combination of
the previous model. This operation reduces the number of computations and helps in
reducing overfitting. After this layer, we apply two parallel convolutions with different
kernel size to capture missing features from the previous layer and concatenate their
outputs to achieve a richer set of features.

To reduce the overfitting on the dataset, many of the layers which were removed are a
Fire module and an Upsampling module. The appropriate skip connections are rerouted
after these changes. The channel dimensions are also significantly reduced and dropout.

The Tversky Index (TI) is an asymmetric similarity measure that is a generalization of
the dice coefficient and the Jaccard index. Unlike BCE, trersky coefficient only
considers the segmentation class and not the background class. The pixels are classified
as True Positive (TP), False Negative (FN), and False Positive (FP). The Tversky
coefficient is a measure of the overlap of the predicted mask and the ground truth.
Since it does not account for the background class, it cannot dominate over the smaller
segmentation class.

## Results
<img width="500" alt="image" src="https://github.com/Ananth864/Forest-Fire-Detection-and-Segmentation/assets/85446106/c924cd83-aed2-4ff9-9970-fefdb076a81a">
<img width="500" alt="image" src="https://github.com/Ananth864/Forest-Fire-Detection-and-Segmentation/assets/85446106/dedd0949-3441-4787-ab9e-4c1bb437dd2b">



