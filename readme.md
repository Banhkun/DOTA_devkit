### Usage
1. For read and visualize data, you can use DOTA.py
2. For evaluation the result, you can refer to the "dota_evaluation_task1.py" and "dota_evaluation_task2.py"
3. For split the large image, you can refer to the "ImgSplit"
4. For merge the results detected on the patches, you can refer to the ResultMerge.py

An example is shown in the demo.
The subdirectory of "basepath"(which is used in "DOTA.py", "ImgSplit.py") is in the structure of
```
.
├── images
└── labelTxt
```

## Prepare DOTA dataset.
It is recommended to symlink the dataset root to `AerialDetection/data`.

Here, we give an example for single scale data preparation of DOTA-v1.0.

First, make sure your initial data are in the following structure.
```
data/dota
├── train
│   ├──images
│   └── labelTxt
├── val
│   ├── images
│   └── labelTxt
└── test
    └── images
```
Split the original images and create COCO format json. 
```
python DOTA_devkit/prepare_dota1.py --srcpath path_to_dota --dstpath path_to_split_1024
```
Then you will get data in the following structure
```
dota1_1024
├── test1024
│   ├── DOTA_test1024.json
│   └── images
└── trainval1024
     ├── DOTA_trainval1024.json
     └── images
```
For data preparation with data augmentation, refer to "DOTA_devkit/prepare_dota1_aug.py"

For data preparation of dota1.5, refer to "DOTA_devkit/prepare_dota1_5.py" and "DOTA_devkit/prepare_dota1_5_aug.py"

