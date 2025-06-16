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

## Part 2: MPM Parameter Effect
### YouTube Video Demo
Link: https://youtu.be/MTRtcbhro4E

### Insight
- n_grid：降低 n_grid 時，撕裂效果明顯下降，甚至出現整體向右漂移的現象，推測是因為在粗網格解析度下，數值積分誤差隨時間累積所導致。推測PSNR在n_grid降低時也會明顯下降。
- substep_dt：調整 substep_dt 影響不明顯。推測PSNR不會差太多。
- grid_v_damping_scale：當降低 grid_v_damping_scale 時，阻尼效果增強，使得粒子較不容易受到外力影響，因此會集中在中心位置。推測PSNR在 grid_v_damping_scale降低時也會明顯下降。
- softening：調整 softening 影響不明顯（可能對這兩個材料來說受力較小，還在材料彈性區間）。推測PSNR不會差太多。
（因為沒有記錄到PSNR目前只用推測的）

### Metal Setting
| Trial| n_grid | substep_dt |grid_v_damping_scale | softening |
|:-------:|:-------:|:-------:|:-------:|:-------:|
| Base | 150     | 10^(-4)     |0.9995      |0.1    |
| 1    |**15**   | 10^(-4)     |0.9995      |0.1    |
| 2    |150     | **10^(-3)**     |0.9995      |0.1    |
| 3    |150     | 10^(-4)     |**0.8**      |0.1    |
| 4-1    |150     | 10^(-4)     |0.9995      |**0**    |
| 4-2    |150     | 10^(-4)     |0.9995      |**0.5**    |

**Base**

https://github.com/user-attachments/assets/7c0ff51a-1a56-4757-843e-948331c800bc

**1**

https://github.com/user-attachments/assets/acb9c88b-556f-48c2-8d0c-cb99d3fe2271

**2**

https://github.com/user-attachments/assets/d2b5dc1f-ec2e-47f3-8f5a-034d1100dea6

**3**

https://github.com/user-attachments/assets/04179fe8-dd1b-4210-b4de-e32ba0b6ea32

**4-1**

https://github.com/user-attachments/assets/f0aadd4a-0821-4c53-9870-379db8f2339c

**4-2**

https://github.com/user-attachments/assets/1ccb3c33-3ab3-4c5c-84d2-da1a69c5f15b



### Sand Setting
| Trial| n_grid | substep_dt |grid_v_damping_scale | softening |
|:-------:|:-------:|:-------:|:-------:|:-------:|
| Base | 150     | 10^(-4)     |0.9995      |0.1    |
| 1    |**15**   | 10^(-4)     |0.9995      |0.1    |
| 2-1    |150     | **10^(-3)**     |0.9995      |0.1    |
| 2-2   |150     | **5 * 10^(-3)**     |0.9995      |0.1    |
| 3    |150     | 10^(-4)     |**0.8**      |0.1    |
| 4-1    |150     | 10^(-4)     |0.9995      |**0**    |
| 4-2    |150     | 10^(-4)     |0.9995      |**0.00001**    |


**Base**

https://github.com/user-attachments/assets/41e4085d-f488-4d91-bc62-f9d93888b4b6

**1**

https://github.com/user-attachments/assets/2c37fcb1-5bb6-41b7-8a35-622560047d47

**2-1**

https://github.com/user-attachments/assets/8aaf3c75-5ab5-455c-a2e0-dae86b6ee040

**2-2**

https://github.com/user-attachments/assets/d6af7a97-cd19-40f6-8d2f-c44e36186dd5

**3**

https://github.com/user-attachments/assets/0cd567eb-58ad-4091-a4f4-0c847c45bb38

**4-1**

https://github.com/user-attachments/assets/bc0c397b-848d-4bf7-bddf-566ee34f6a34

**4-2**

https://github.com/user-attachments/assets/3228e8b7-aa67-44ac-986a-a042bf272d0a

# Reference
```bibtex
@inproceedings{xie2024physgaussian,
    title     = {Physgaussian: Physics-integrated 3d gaussians for generative dynamics},
    author    = {Xie, Tianyi and Zong, Zeshun and Qiu, Yuxing and Li, Xuan and Feng, Yutao and Yang, Yin and Jiang, Chenfanfu},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
    year      = {2024}
}
```
