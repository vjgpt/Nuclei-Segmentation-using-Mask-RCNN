# Nuclei-Segmentation-using-Mask-RCNN

Goal of this project was to create an algorithm to automate nucleus detection from biomedical images.
By automating nucleus detection, we could help unlock cures faster—from rare disorders to the common cold.

# Model Oveview

For this competition, I modified [Matterport's](https://github.com/matterport/Mask_RCNN) implementation of Mask-RCNN deep neural network for object instance segmentation. I adapted the existing model configurations to detect small nuclei in images with varying size and modality. To ensure that the model doesn't overfit, I used image augmentation on all the train dataset.

- `mrcnn` folder contain the model files and configuration from Mask-RCNN.
- `main.py` has wrapped up everything from training to detection.

# Command Line Usage

Train a new model starting from ImageNet weights using train dataset (which is stage1_train minus validation set)

`python3 nucleus.py train --dataset=/path/to/dataset --subset=stage1_train --weights=/path/to/weights.h5`

Resume training a model that you had trained earlier

`python3 nucleus.py train --dataset=/path/to/dataset --subset=train --weights=last`

Generate submission file from stage1_test images

`python3 nucleus.py detect --dataset=/path/to/dataset --subset=stage1_test --weights=<last or /path/to/weights.h5>`

### Notebook to be uploaded soon for the inspecting of test dataset. 
