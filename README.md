# A Multi Scale Coarse to Fine Human Pose Estimation Network with Hard Keypoint Mining

## Introduction
This is an pytorch implementation of 《A Multi Scale Coarse to Fine Human Pose Estimation Network with Hard Keypoint Mining》. 
Current convolution neural network (CNN)-based
multi-person pose estimators have achieved great progress, however,
they pay no or less attention to “hard” samples, such as
occluded keypoints, small and nearly invisible keypoints, and
ambiguous keypoints. In this paper, we explicitly deal with
these “hard” samples by proposing a novel multi-scale coarse-tofine
human pose estimation network (HM2PN). </br>

![Illustrating the architecture of the proposed HM2PN](/figures/HM2PN.jpg)
## Main Results
### Results on COCO val2017
| Arch               | Input size | #Params | GFLOPs |    AP | Ap .5 | AP .75 | AP (M) | AP (L) |    AR |
|--------------------|------------|---------|--------|-------|-------|--------|--------|--------|-------|
| HRNet_w32 |    256x192 | 28.5M   |    7.1 | 0.744 | 0.905 |  0.819 |  0.708 |  0.810 | 0.798 |
| HRNet_w32 |    384x288 | 28.5M   |   16.0 | 0.758 | 0.906 |  0.825 |  0.720 |  0.827 | 0.809 |
| HRNet_w48 |    256x192 | 63.6M   |   14.6 | 0.751 | 0.906 |  0.822 |  0.715 |  0.818 | 0.804 |
| HRNet_w48 |    384x288 | 63.6M   |   32.9 | 0.763 | 0.908 |  0.829 |  0.723 |  0.834 | 0.812 |
| **HM2PN_w32** |    256x192 | 28.4M   |   7.4 | 0.765 | 0.936 |  0.836 |  0.735 |  0.807 | 0.793 |
| **HM2PN_w32** |    384x288 | 28.4M   |   15.9 | 0.777 | 0.937 |  0.842 |  0.744 |  0.823 | 0.794 |
| **HM2PN_w48** |    256x192 | 63.5M   |   14.9 | 0.771 | 0.936 |  0.838 |  0.741 |  0.814 | 0.798 |
| **HM2PN_w48** |    384x288 | 63.5M   |   32.8 | 0.781 | 0.938 |  0.845 |  0.748 |  0.830 | 0.806 |

### Note:
- Flip test is used.
- Detector for the person category has person AP of 56.4 on COCO val2017 dataset.
- GFLOPs is for convolution and linear layers only.


### Results on COCO test-dev2017 with detector having human AP of 60.9 on COCO test-dev2017 dataset
| Arch               | Input size | #Params | GFLOPs |    AP | Ap .5 | AP .75 | AP (M) | AP (L) |    AR |
|--------------------|------------|---------|--------|-------|-------|--------|--------|--------|-------|
| **HM2PN_w32** |    384x288 | 28.4M   |   15.9 | 0.767 | 0.950 |  0.842 |  0.736 |  0.803 | 0.784 |
| **HM2PN_w48** |    384x288 | 63.5M   |   32.8 | 0.771 | 0.950 |  0.848 |  0.743 |  0.810 | 0.798 |
| **HM2PN_w48+UDP** |    384x288 | 63.7M   |   32.4 | 0.779 | 0.952 |  0.850 |  0.753 |  0.818 | 0.805 |

### Note:
- Flip test is used.
- Detector for the person category has person AP of 60.9 on COCO test-dev2017 dataset.
- GFLOPs is for convolution and linear layers only.
-UDP means  [*The Devil is in the Details: Delving into Unbiased Data Processing for Human Pose Estimation*]https://github.com/HuangJunJie2017/UDP-Pose/blob/master/README.md).


## Environment
The code is developed using python 3.6 on Ubuntu 16.04. The code is developed and tested using NVIDIA GTX1080TI GPU cards. Other platforms or GPU cards are not fully tested.

## Quick start
Please refer to [HRNet](https://github.com/leoxiaobin/deep-high-resolution-net.pytorch)

