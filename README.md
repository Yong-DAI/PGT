# PGT
Official code for the manuscript "Dual-Attention Based Prompt Generation and Transformation for Instance-wise Continual Learning" which is submitted to AAAI and will be online recently.

## Main focus: 
Prior works learn to directly select and tune task-level prompts based on the task ID predicted by similarity calculation, which is limited by the erratic selection step and coarse-grained instructions when handling successive tasks. Our work firstly introduces fine-grained instance-specific prompts generated based on layer attention between layer-wise features and naive features, which is then followed by a prompt affine transformation step to make the prompt adaptive to different tasks based on the task-level affine parameters derived from anchor attention. Unlike prior work, our work learns more fine instance-specific prompts and circumvents the needs of the selection step.


if you are interested in our work, please feel free to contact me by chd-dy@foxmail.com


This repository contains the implementation details of our Prompt Generation and Transformation approach for continual learning with transformer backbone.

## Requirements
The code is written for python `3.8.18`, but should work for other version with some modifications.
```
pip install -r requirements.txt
```
## Data preparation
If you already have CIFAR-100/ImageNet-R/CUB-200, pass your dataset path to the `--data-path` argument during execution
(If they aren't ready they will automatically get downloaded to the data-path mentioned when the `download` argument is kept True in `datasets.py`).



## Training
Use the following command for training:

```
export TOKENIZERS_PARALLELISM=false
python -m main <cifar100_pgt > \
        --num_tasks 10 \
        --data-path /local_datasets/ \
        --output_dir ./output 
```


## Acknowledgement

This repo is heavily based on the  [DualPrompt](https://github.com/JH-LEE-KR/dualprompt-pytorch) and [ConvP](https://cvir.github.io/projects/convprompt) Implementations. We thank them for their wonderful work!






