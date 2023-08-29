Data and code for "ZS-ViDAT: Visual descriptions using an Attribute-governed Transformer for zero-shot scene classification in remote sensing images"

Run the following codes one after the other.
--------------------------------------------------------------------------
		mataw.py
--------------------------------------------------------------------------
Initially, set the dataset path and run mataw.py file.
This code will generate {dataset}_img/_label.csv files which contains: labels:- label number of a class is its row number in {dataset}classes.txt and image_files:- image sources


--------------------------------------------------------------------------
mat_create.m
--------------------------------------------------------------------------
Code to create res101.mat file that contains image_files and labels.


--------------------------------------------------------------------------
dataset_create.py
--------------------------------------------------------------------------
Initially, set the dataset path and run mataw.py file.
code to obtain att_splits.mat file, according to standard splits in remote sensing, we split the dataset. 
Inorder to obtain different splits, change the variable test_seen in this file according to standard splis (for eg., test_seen=16 is one of the standard splits in UCM21 dataset (16/5)), and also change random seed for every new split.

Then, place res101.mat and att_splits.mat files in ZS-ViDAT/data/xlsa17/data/{dataset}/...


----------------------------------------------------------------------------
Data
----------------------------------------------------------------------------

resNet101.mat includes the following fields:
-labels: label number of a class is its row number in allclasses.txt
-image_files: image sources  


att_splits.mat includes the following fields:
-att: columns correpond to class attribute vectors normalized to have unit l2 norm, following the classes order in {dataset}classes.txt 
-original_att: the original class attribute vectors without normalization
-trainval_loc: instances indexes of train+val set features (for only seen classes) in resnet101.mat
-test_seen_loc: instances indexes of test set features for seen classes
-test_unseen_loc: instances indexes of test set features for unseen classes
