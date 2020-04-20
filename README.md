# MLSP feature learning on AVA 

This is part of the code for the paper ["Effective Aesthetics Prediction with Multi-level Spatially Pooled Features"](http://openaccess.thecvf.com/content_CVPR_2019/papers/Hosu_Effective_Aesthetics_Prediction_With_Multi-Level_Spatially_Pooled_Features_CVPR_2019_paper.pdf). Please cite the following paper if you use the code:

```
@inproceedings{hosu2019effective,
  title={Effective Aesthetics Prediction with Multi-level Spatially Pooled Features},
  author={Hosu, Vlad and Goldlucke, Bastian and Saupe, Dietmar},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={9375--9383},
  year={2019}}
```
Multi-level Spatially-Pooled (MLSP) features extracted from ImageNet pre-trained Inception-type networks are used to train aesthetics score (MOS) predictors on the Aesthetic Visual Analysis (AVA) database. The code shows how to train models based on both narrow and wide MLSP features. Several fully trained [models](https://github.com/subpic/ava-mlsp/tree/master/models) are included, together with demos on how to apply them on new images. The models are stored with git LFS, and they can be [downloaded from here](https://osf.io/ubps5/files/) as well. The included notebooks rely on the [kutils library](https://github.com/subpic/kutils).

## Deployment

There are several options to run the code:

1. Create your own Python environment:
```
Python 2.7.16
tensorflow-gpu 1.14.0
keras-gpu 2.2.4
```

2. Run it on google colab, see [example notebook (py3)](https://bit.ly/AVA-MLSP) for prediction.

3. Deploy the code via the Dockerimage in [jupyter-data-science](https://github.com/subpic/jupyter-data-science), with the Python 2 environment.

## Overview

The following files are included:

**`extract_mlsp.ipynb`**:

- Extract MLSP features from AVA images and save them to HDF5 files; allows storing per image augmentions.

**`train_mlsp_narrow.ipynb`**, **`train_mlsp_narrow_aug.ipynb`**

- Train on narrow MLSP features (1&times;1&times;16k) from InceptionResNet-v2 with and without augmentation applied before storing features (crops, flips).

**`train_mlsp_wide.ipynb`**

- Train on wide MLSP features (5&times;5&times;16k) from InceptionResNet-v2 without augmentation.

**`predict_mlsp_wide.ipynb` ([open on google colab (py3)](https://bit.ly/AVA-MLSP))**

- Assembles pre-trained [model](https://github.com/subpic/ava-mlsp/tree/master/models) that predicts scores directly from images (rather than saved MLSP features).

**`metadata/AVA_data_official_test.csv`**

- Contains image meta-data, including file names, corresponding scores, resolutions and the membership in the [test](https://github.com/mtobeiyf/ava_downloader/blob/master/AVA_dataset/aesthetics_image_lists/generic_test.jpgl)/validation/train split.
