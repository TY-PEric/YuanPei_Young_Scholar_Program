# YuanPei_Young_Scholar_Program
This project builds upon the foundational machine learning and deep learning research conducted during my participation in the **Yuanpei Young Scholars (YSA)** program (Computer Vision Research Track). 

## Skeleton-Based Sign Language Recognition

This repository contains the research paper and experimental Jupyter notebooks for my project on translating World-Level American Sign Language (WLASL) into English words using computer vision and skeleton-based action recognition.

### Project Overview
Sign language is a visual language that relies on complex hand gestures, body postures, and facial expressions. Traditional SLR models struggle with high accuracy. In this research, I reproduced and compared two skeleton-based frameworks:
* **SL-GCN** (Sign Language Graph Convolution Network) 
* **SSTCN** (Separable Spatial Temporal Convolution Network)

The models were evaluated on the Word-Level American Sign Language Recognition (WLASL) dataset, converting video inputs into skeleton graphs for deep learning classification.

### Key Results
Our implementation successfully reproduced the baseline results, proving the effectiveness of multi-stream approaches:
* **Multi-stream SL-GCN:** Achieved **95.45%** Top-1 Accuracy and **99.25%** Top-5 Accuracy.
* **SSTCN (24x24 feature size):** Achieved **94.32%** Top-1 Accuracy.

### Repository Structure
* `Skeleton_Based_Sign_Language_Recognition_Report.pdf`: The complete research paper including methodology, data tables, and deployment discussions.
* `*.ipynb` (Colab Notebooks): Experimental code and coursework notebooks used during the project to test models and process the WLASL dataset from PapersWithCode.

### Tech Stack & Challenges
* **Tools:** Python, Deep Learning (GCN/CNN), Google Colab.
* **Deployment:** Handled environment configuration and code migration on **Tencent Cloud Servers**. (Detailed in the Discussion section of the paper).
