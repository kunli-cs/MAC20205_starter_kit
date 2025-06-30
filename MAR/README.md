# Micro-Action Analysis Grand Challenge

The baseline code for Track 1: Micro-Action Recognition (MAR) of [The 2nd Micro-Action Analysis Grand Challenge](https://sites.google.com/view/micro-action) hosted in [ACM MM 2025](https://acmmm2025.org/). 

## Data Preparation

Fetch the video data from [Challenge page](https://sites.google.com/view/micro-action/datasets), and place it to `./data`.

---

## 🛠️ Installation
This code build based on [MMAction2](https://github.com/open-mmlab/mmaction2). 
<summary>Quick instructions</summary>
<details close>

```shell
conda create --name openmmlab python=3.8 -y
conda activate openmmlab
conda install pytorch torchvision -c pytorch  # This command will automatically install the latest version PyTorch and cudatoolkit, please check whether they match your environment.
pip install -U openmim
mim install mmengine
mim install mmcv
mim install mmdet  # optional
mim install mmpose  # optional
git clone https://github.com/kunli-cs/MAC20205_starter_kit.git
cd MAC20205_starter_kit/MAR/mmaction2
pip install -v -e .
```
</details>

---

## 🔥 Train
You can use the following command to train a model.
```shell
# Swin Video Transformer base version
python tools/train.py configs/recognition/swin/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb.py --seed=0 --deterministic
```

---
## Test

```shell

python tools/test.py configs/recognition/swin/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb.py work_dirs/swin/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb/best_acc_top1_epoch_33.pth --dump submit/test_result.pickle
## build the submission file
python ./submit/generate.py
## Note that this code is for Development Phase.


##########################
# Testing Phase
##########################
### Swin-base
python tools/test.py configs/recognition/swin/swin-base-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb.py work_dirs/swin/swin-base-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb/best_acc_top1_epoch_39.pth --dump submit/test_result.pickle
## build the submission file
python ./submit/generate.py


### Swin-small
python tools/test.py configs/recognition/swin/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb.py work_dirs/swin/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb/best_acc_top1_epoch_33.pth --dump submit/test_result.pickle
## build the submission file
python ./submit/generate.py

```

---
## Results on validation set

| Model | Top-1 (Body) | Top-1 (Action) | F1_mean | ckpt |
| :-: | :-: | :-: | :-: | :-: |
| VSwin-base | 78.59 | 61.15 | 65.18 | [Link 🤗](https://huggingface.co/kunli-cs/VSwin_MA52_Weights/tree/main/swin-base-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb) |
| VSwin-small | 79.18 | 61.37 | 65.92 | [Link 🤗](https://huggingface.co/kunli-cs/VSwin_MA52_Weights/tree/main/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb) |

## Results on test set (1138 samples)

| Model | Top-1 (Body) | Top-1 (Action) | F1_mean | ckpt |
| :-: | :-: | :-: | :-: | :-: |
| VSwin-base | 77.15 | 60.19 | 64.57 | [Link 🤗](https://huggingface.co/kunli-cs/VSwin_MA52_Weights/tree/main/swin-base-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb) |
| VSwin-small | 79.44 | 58.96 | 65.68 | [Link 🤗](https://huggingface.co/kunli-cs/VSwin_MA52_Weights/tree/main/swin-small-p244-w877_in1k-pre_8xb8-amp-32x2x1-40e_ma52-rgb) |

**Note that the test set (1138 samples) of Track 1 is a subset sampled from the original test (5526 samples) set of the MA-52 dataset.**

## Acknowledgments
This code began with [MMAction2](https://github.com/open-mmlab/mmaction2). We thank the developers for doing most of the heavy-lifting.

---
## Citation
Please consider citing the related paper in your publications if it helps your research.
```
@article{guo2024benchmarking,
  title={Benchmarking Micro-action Recognition: Dataset, Methods, and Applications},
  author={Guo, Dan and Li, Kun and Hu, Bin and Zhang, Yan and Wang, Meng},
  journal={IEEE Transactions on Circuits and Systems for Video Technology},
  year={2024},
  volume={34},
  number={7},
  pages={6238-6252},
}



```
---

## Contact
**For any questions, feel free to contact: [kunli.hfut@gmail.com](mailto:kunli.hfut@gmail.com?subject=Micro-Action%20Grand%20Chanllenge).**
