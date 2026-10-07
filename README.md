# Skeleton-Based Sign Language Recognition: SAM-SLR Reproduction

Final project from the Yuanpei Young Scholars computer vision program (2023-24). I reproduced the two skeleton-based models from **SAM-SLR** (Jiang et al., *Skeleton Aware Multi-modal Sign Language Recognition*, CVPR 2021 Workshops) using the authors' released code and pretrained checkpoints, and wrote a short report on how they work.

## The models
* **SL-GCN**: a graph convolutional network over 27 whole-body keypoints, reduced from the 133 that the pose estimator outputs. Four streams (joint, bone, joint motion, bone motion) run separately and are combined with a weighted ensemble. Each block has a decoupled spatial graph convolution, spatial/temporal/channel attention, a temporal convolution, and DropGraph.
* **SSTCN**: a separable spatial-temporal convolutional network on features from 33 keypoints over 60 frames.

## What I did
* Set up the authors' code ([jackyjsy/CVPR21Chal-SLR](https://github.com/jackyjsy/CVPR21Chal-SLR)) and pretrained checkpoints on a Tencent Cloud server. Cloning over HTTPS and SSH both failed on that server, so I uploaded the code as an archive. The Discussion section of the report covers the setup problems.
* Ran the four SL-GCN streams, the multi-stream ensemble, and SSTCN, and checked the outputs against the paper's tables.
* Wrote the report (`Skeleton_Based_Sign_Language_Recognition_Report.pdf`): method, results, and limits (word-level output only; benchmark videos are much cleaner than real-world footage).

## Note on the report's results
The released checkpoints come from the CVPR 2021 ChaLearn challenge and were trained on **AUTSL** (Turkish Sign Language, 226 signs). The result tables in the report (Figures 5 and 6) are **AUTSL validation** figures and match the SL-GCN and SSTCN tables in the SAM-SLR paper. The report and an earlier version of this README described them as WLASL-2000 results, which was wrong: SAM-SLR's WLASL-2000 Top-1 accuracy is under 60% (58.73% in the report's own Figure 3).

## Other files
The three notebooks are coursework from the program's deep learning bootcamp, not part of the sign language pipeline:
* `Deep_Learning_in_Practice_Bootcamp.ipynb`: PyTorch training template (Dataset class, DataLoaders, loss, optimizer and scheduler, Weights & Biases logging)
* `Deep_learning_in_spaceship_titanic.ipynb`: the same template applied to the Kaggle Spaceship Titanic dataset
* `YSA_FW23_Group_4_HW_1_ipynb_resnet50.ipynb`: group homework, ResNet-50 image classification with a Kaggle submission

## Credit
The model code and checkpoints are the work of the SAM-SLR authors (Songyao Jiang, Bin Sun, Lichen Wang, Yue Bai, Kunpeng Li, Yun Fu). Paper: https://arxiv.org/abs/2103.08833
