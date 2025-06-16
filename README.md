[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/SdXSjEmH)
# EV-HW3: PhysGaussian

This homework is based on the recent CVPR 2024 paper [PhysGaussian](https://github.com/XPandora/PhysGaussian/tree/main), which introduces a novel framework that integrates physical constraints into 3D Gaussian representations for modeling generative dynamics.

You are **not required** to implement training from scratch. Instead, your task is to set up the environment as specified in the official repository and run the simulation scripts to observe and analyze the results.


## Getting the Code from the Official PhysGaussian GitHub Repository
Download the official codebase using the following command:
```
git clone https://github.com/XPandora/PhysGaussian.git
```


## Environment Setup
Navigate to the "PhysGaussian" directory and follow the instructions under the "Python Environment" section in the official README to set up the environment.


## Running the Simulation
Follow the "Quick Start" section and execute the simulation scripts as instructed. Make sure to verify your outputs and understand the role of physics constraints in the generated dynamics.


## Part 1: 2 materials
### Metal
https://github.com/user-attachments/assets/7c0ff51a-1a56-4757-843e-948331c800bc
### sand
https://github.com/user-attachments/assets/41e4085d-f488-4d91-bc62-f9d93888b4b6

## Part 2: MPM Parameter Effet
### n_grid
| material\n_grid | 150(original) | 15 |
|-------|-------|-------|
| metal | https://github.com/user-attachments/assets/7c0ff51a-1a56-4757-843e-948331c800bc | https://github.com/user-attachments/assets/0df5b33d-dd26-43f6-8f2f-113c8a7dd0ca |
| sand  | https://github.com/user-attachments/assets/41e4085d-f488-4d91-bc62-f9d93888b4b6 | https://github.com/user-attachments/assets/5523779b-5b1d-40c8-9060-5753981640f7 |





| 欄位1 | 欄位2 | 欄位3 |
|-------|-------|-------|
| A     | B     | C     |
| D     | E     | F     |

### substep_dt

### grid_v_damping_scale

### softening

# Reference
```bibtex
@inproceedings{xie2024physgaussian,
    title     = {Physgaussian: Physics-integrated 3d gaussians for generative dynamics},
    author    = {Xie, Tianyi and Zong, Zeshun and Qiu, Yuxing and Li, Xuan and Feng, Yutao and Yang, Yin and Jiang, Chenfanfu},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
    year      = {2024}
}
```
