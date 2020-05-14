# Food-Pav_bhaji-detection
Project for detecting a particular type of food item (pav bhaji - one must try this, it's delicious!!!) in images.



The aproach makes use of transfer-learning . The model used here is VGG16 model which was pre-trained on image-net. In addition to this, a shallow CNN is also used which is then concatenated with the VGG16. This combined model is trained on the current dataset while not retraining the VGG16. Initially, I thought json data could also be used as an addtional input to the architecture (in that case parallel layers could have been concatenated, i.e. VGG16 + Shallow CNN + the parallel model for json). But, the problem with json file was that ,for all the images, words like "pav bhaji","#pav-bhaji" were present in the caption even for the non-paav bhaji images. Therefore, in the end, just the image has been solely used for the clssification task and was able to achieve F1 score of .8. Stratified sampling was also used to account for the imbalance in the class distribution.
