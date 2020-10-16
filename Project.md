# Project Notes

### Exploits

1. Public test set ~65% R
2. Can initially find all benign vs cancerous by exploiting metric
3. Split the dataset and train a classifier for each center

For phase 1, maybe leave out images with lots of Gleason 2 to make the model more clearly distinguish.



### Pipeline


Initial idea
1. Split dataset
2. Mean normalization
3. Create Patches
4. CycleGAN to Normalize
5. Deep CNN to Classify Patches
6. Featurize predictions
7. kNN/DT for ISUP




Methodical

Divide the problem into components and devise a scoring metric for each step

C1.
 - Action: Split the input image into patches
 - Score:  Can the patch mask predict the output?

 Trials:
 	Strategies:
 		- Top 12 by mean pixel value
 		- Random 12
 		- All

 			Radboud	Karolinska
 	Top12	0.87	0.95
 	Ran12	0.81	0.91
 	All 	0.94	0.99


 Extraction format:
 Filename: Provider_PatchSelectionMethod_ZoomLevel_PatchSizes
 File format:
 	CSV
 	Header: Image_id, Patch_id, x, y, isup, mask_0, mask_1, mask_2, mask_3, mask_4, mask_5


 R_T12_1_512
 K_T12_1_512





List of Models for Ensemble
R-RN
Radboud-ResNet

R-EN
Radboud-EfficientNet





### Possible CNN Backbones
 - densenet121
 - seresnet50