# MLSP feature learning on AVA 

This is part of the code for the paper ["Effective Aesthetics Prediction with Multi-level Spatially Pooled Features"](http://openaccess.thecvf.com/content_CVPR_2019/papers/Hosu_Effective_Aesthetics_Prediction_With_Multi-Level_Spatially_Pooled_Features_CVPR_2019_paper.pdf). The included notebooks rely on the [kutils library](https://github.com/subpic/kutils).

Multi-level Spatially-Pooled (MLSP) features extracted from ImageNet pre-trained Inception-type networks are used to train aesthetics score (MOS) predictors on the Aesthetic Visual Analysis (AVA) database. The code shows how to train models based on both narrow and wide MLSP features. Several fully trained [models](https://github.com/subpic/ava-mlsp/tree/master/models) are included, together with demos on how to apply them on new images.

## Overview

Demo Python 2.7 notebooks:

**`extract_mlsp.ipynb`**:

- Extract MLSP features from AVA images and save them to HDF5 files; allows storing per image augmentions.

**`train_mlsp_narrow.ipynb`**, **`train_mlsp_narrow_aug.ipynb`**

- Train on narrow MLSP features (1&times;1&times;16k) from InceptionResNet-v2 with and without augmentation applied before storing features (crops, flips).

**`train_mlsp_wide.ipynb`**

- Train on wide MLSP features (5&times;5&times;16k) from InceptionResNet-v2 without augmentation.

**`predict_mlsp_wide.ipynb`**

- Assembles pre-trained [model](https://github.com/subpic/ava-mlsp/tree/master/models) that predicts scores directly from images (rather than saved MLSP features).

**`metadata/AVA_data_official_test.csv`**

- Contains image meta-data, including file names, corresponding scores, resolutions and the membership in the [test](https://github.com/mtobeiyf/ava_downloader/blob/master/AVA_dataset/aesthetics_image_lists/generic_test.jpgl)/validation/train split.

