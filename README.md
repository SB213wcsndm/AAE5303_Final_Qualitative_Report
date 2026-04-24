# AAE5303 Individual Report on Six Qualitative Indicators

## 1. Metadata

| Item | Details |
|---|---|
| Course | AAE5303 |
| Report type | Individual Report on Six Qualitative Indicators |
| Student name | ZHANG Yuhao |
| Student ID | 25044023G |
| Team name / group number | 我們組 (WMZ) |
| Team repo URL | https://github.com/mcllouie/AAE5303_Final-project_--WMZ |
| My role in the team | 3D scene reconstruction |
| My primary module | [~~VSLAM~~ / 3D reconstruction / ~~segmentation / integration / benchmarking~~ / other] |
| Main dataset / scene used | AMtown02 |
| Main tools used | Cursor / Docker / ROS / ~~ORB-SLAM3~~ / OpenSplat / ~~U-Net~~ / others |
| Main evidence paths | https://github.com/SB213wcsndm/AAE5303_opensplat_demo-.git |
| ~~Commit hash(es) / issue / notebook~~ / slide links | https://mcllouie.github.io/AAE5303-Group_Project-WMZ_Slides/ |
| Declared AI use | Doubao and Cursor Agent |

---

## 2. Individual Contribution Statement

| Item | Content |
|---|---|
| Team result | Using the first 20 images of AMtown02 as the dataset |
| My specific role | 3D scene reconstruction |
| My strongest evidence |  Using completely AMD CPU to complete the 3D scene reconstruction  |
| My main learning focus |  How to build OpenSplat local and generate 3D models from datasets after training  |

---

## 3. Project Snapshot

### 3.1 Project goal
To complete the 3 pipelines using the AMtown02 dataset, with the below challenges:

1, Using completely MacOS with Apple Silicon to complete the Visual SLAM.
2, TAs had shut down the server JUST BEFORE REPORT DATE without prior notification, that computing 3DGS with notebook computers without GPU is an issue.
3, U-Net have given a complete guide, but without hands-on.
Anyway, we successfully completed.

### 3.2 Pipeline overview
Since the dataset (AMtown02) was given by HKU MaRS Lab, we are able to perform 3 pipelines at the same time. The pipeline for VO mainly follows the instructions and experiences from assignment 2 by Man Chi Lok Louie. 3DGS was originally planned to use the server provided by TAs, yet it is shut off JUST BEFORE REPORT DATE, so I have to complete it locally. For segmentation, its Bailin's specialties that he could complete the task swiftly.

### 3.3 My position in the pipeline
My position is 3D scene reconstruction. Because after the server was shut down, I need to build OpenSplat on CPU and finish the 3D scene reconstruction task on a unperfect prarmeters and train situations.

### 3.4 Reproducibility snapshot
| Item | Details |
|---|---|
| Main environment | Dell Inspiron 5485 with AMD Ryzen 5 3500U CPU and 8.00 GB RAM (Using WSL2 Ubuntu 20.04) |
| Key scripts / folders | https://github.com/SB213wcsndm/AAE5303_opensplat_demo-/blob/main/training_report1.json |
| Main evaluation scripts | https://github.com/SB213wcsndm/AAE5303_opensplat_demo-/blob/main/baseline/evaluate_baseline.py |
| Main figures in this report | https://github.com/SB213wcsndm/AAE5303_opensplat_demo-/blob/main/summary_dashboard.png |
| What another person should run first | https://github.com/SB213wcsndm/AAE5303_opensplat_demo-/blob/main/README.md |

---

## 4. Six-Indicator Summary Matrix

| Indicator | Before-course (optional) | End-of-course | Main evidence | Main lesson |
|---|---:|---:|---|---|
| 1. Tooling & Reproducible Workflow Readiness | 1 | 4 | AMD CPU and WSL2 Ubuntu | Without a CUDA-capable GPU led to excessively high CPU usage and eventually a system breakdown. |
| 2. Prompting Strategy & AI Co-Creation | 1 | 4 | Reduced Drifting of IMU | Cursor may modify my files automatically based on its generated outputs. |
| 3. Verification, Documentation & Technical Judgment | 3 | 4 | PPT is finished | Still exist problems such as consistency with the English expression. |
| 4. Debugging, Iteration & Problem Solving | 1 | 4 | Solved system lag and crash problem | Using a CUDA-capable GPU or Server can improve precision and speed. |
| 5. Integration & Benchmark-Driven Improvement | 1 | 3 | Can obtain 3D scene reconstruction result | There are limitation with datasets, training times and parameters. |
| 6. Responsible AI Use, Reflection & Redesign | 2 | 3 | 3D scene reconstruction completed in AMD CPU and the reduce of losses by OpenSplat is proved | Cursor may led to error parameters or modify my files automatically based on its generated outputs. |

---

## 5. Indicator 1 - Tooling & Reproducible Workflow Readiness

**Before-course confidence (optional):** `1/5`

**End-of-course confidence:** `4/5`

### Situation / task
To complete 3D scene reconstruction in AMD CPU.

### What I did
Follow and verify the operation procedure from the course materials and Cursor.

### Evidence
<img width="1908" height="894" alt="13e04b649c16ba9d2b9901259ae16164" src="https://github.com/user-attachments/assets/6cfbe43f-e6ce-4479-938d-e23ec5651c49" />

### What this shows
3D scene reconstruction in AMD CPU is completely feasible.

### Limitation
Since my device is equipped with an AMD CPU and does not have a CUDA-architecture GPU, directly executing the command provided by Cursor will result in excessively high CPU usage and cause a crash.

### Next improvement
Use commands that reduce the matching parameters between images to improve running speed under CPU operation.

---

## 6. Indicator 2 - Prompting Strategy & AI Co-Creation

**Before-course confidence (optional):** `1/5` 

**End-of-course confidence:** `4/5`

### Situation / task
To suggest key parameters for feature extraction and feature matching for pose generation.

### What I did
Ask Cursor to provide the key parameters for pose generation then verify and aadjust it on my computer.

### Evidence

```
- Resulting config or code change:
```bash
Feature Extraction:
colmap feature_extractor \             --Invoke the feature_extractor command of COLMAP. 
  --database_path database.db \
  --image_path images \
  --ImageReader.single_camera 1 \              --The same camera intrinsic model 
  --SiftExtraction.use_gpu 0 \                 --Disable GPU and use CPU only
  --SiftExtraction.max_image_size 1000 \       --Limit the long side of images to a maximum of 1000 pixels
  --SiftExtraction.max_num_features 1024 \     --Retain a maximum of 1024 feature points per image
  --SiftExtraction.num_threads 2               --Only use 2 CPU threads

Feature Matching
colmap sequential_matcher \             --Invoke the sequential matching module of COLMAP，instead of exhaustive_matcher for a rapid result 
  --database_path database.db \
  --SiftMatching.use_gpu 0 \                --Disable GPU and use CPU only
  --SequentialMatching.overlap 15 \         --Up to approximately 15 preceding and subsequent frames
  --SiftMatching.max_num_matches 16384 \    --A maximum of 16384 matching points will be retained
  --SiftMatching.num_threads 2              --Only use 2 CPU threads

```
- What the AI still could not solve: Stil Drift.

### What this shows
Ai do know which parameters need to be adjusted.

### Limitation
Ai still not that "super" to solve problems directly, it still needed to adjust after several verifications.

### Next improvement
Try use more images, more training times and better pasrameters.

---

## 7. Indicator 3 - Verification, Documentation & Technical Judgment

**Before-course confidence (optional):** `3/5`

**End-of-course confidence:** `4/5`

### Situation / task
To generate group PPT of my part

### What I did
Prompt: Create a PPT Slides for my presentation of about 6 minutes regarding OpenSplat and 3D Scene Reconstruction, which including Build Process and Training Result Evaluate.

### Evidence
https://github.com/mcllouie/AAE5303-Group_Project-WMZ_Slides

### What this shows
I finished slides with appropriate length for me, with key parameters setting and result evaluation.

### Limitation
Ai could help generate scripts, but still exist problems such as consistency with the English expression.

### Next improvement
It should be review or rewritten by myself.

---

## 8. Indicator 4 - Debugging, Iteration & Problem Solving

**Before-course confidence (optional):** `1/5`  

**End-of-course confidence:** `4/5`

### Situation / task
Solved system lag and crash problem

### What I did
By referring to the official OpenSplat open-source tutorials, I learned how to build OpenSplat for CPU-only operation. Meanwhile, I consulted Cursor and obtained optimized commands that reduced inter-image matching parameters to accelerate runtime performance on the CPU.

### Evidence
Solved system lag and crash problem caused by equmipment limitation.

### What this shows
Excessively high CPU usage when feature extraction or feature matching will cause system lag and crash.

### Limitation
Mainly equipment limitation, my notebook computer limit the parameter setting, training times and dataset decision.

### Next improvement
Maybe using a CUDA-capable GPU or Server can improve precision and speed.

---

## 9. Indicator 5 - Integration & Benchmark-Driven Improvement

**Before-course confidence (optional):** `1/5`  

**End-of-course confidence:** `3/5`

### Situation / task
To achieve a reduction of losses after several times training.

### What I did
Set the times of training to 30 and each 10 times save a intermediate result, and then evaluate these results.

### Evidence
<img width="2076" height="1477" alt="convergence_analysis" src="https://github.com/user-attachments/assets/f7898778-41d0-4169-9aea-35289023e6f7" />


### What this shows
The feature loss decreased by 36.7% after 30 training rounds, dropping from the initial value of 0.2798 to 0.1772. This verified that the reconstruction performance achieved a substantial improvement in this scenario. 

### Limitation
The equipment limitation makes me set only 30 times training.

### Next improvement
Improve training times to have a more intuitive result.

---

## 10. Indicator 6 - Responsible AI Use, Reflection & Redesign

**Before-course confidence (optional):** `2/5`  
**End-of-course confidence:** `3/5`

### Situation / task
3D scene reconstruction parameters improvement.

### What I did
Googling in most part of the project, Gemini at the last part.

### Evidence
3D scene reconstruction completied in AMD CPU, with satisfactory losses reduction.

### What this shows
Though it seemingly hard in first glance, but with Ai and personal hard work, it still could be solved.

### Limitation
Ai is based on previous experience in coding, still can't really generate "new" code.  In other words, those solution are stacking from various sharing from the internet, but not it really generate something new.

### Next improvement
1. To provide more precise prompt.
2. To learn rather than 100% rely on Ai, that I could proof-read.
3. To solve myself and ask Ai to check my design.

---

## 11. Overall Growth Summary
Before taking this course, I had already learned how to use ROS1 Noetic, but I had no prior experience with Docker or Cursor for development. During Assignment 1, I started using Cursor to help troubleshoot and resolve technical errors. For Assignment 2, I pulled Docker images and configured proper docker run commands with Cursor’s guidance to complete the project tasks.

My most significant progress lies in my in-depth understanding of the entire 3D scene reconstruction workflow. I have gained a clear grasp of how each step connects as a complete pipeline, including building the OpenSplat development environment, importing training datasets, feature extraction, feature matching, pose generation, and 3D scene reconstruction. Furthermore, I am now able to comprehend the specific functions and implications of relevant parameters and commands throughout the process, and adjust them appropriately according to actual project requirements.

The application of artificial intelligence has greatly facilitated my study. Cursor is highly effective in helping me troubleshoot errors and provide guidance for the next step, enabling me to fully understand the causes and outcomes of each operation. It has significantly assisted me in completing all assignments and projects.

On the other hand, I found that Cursor’s AI Agent will modify my files automatically based on its generated outputs, including files in the workspace. For instance, during the training initialization phase of the 3D scene reconstruction project, the Agent arbitrarily altered the required pose .bin file in the workspace. This mismatch between the actual images and the modified pose .bin file prevented the training process from starting successfully. This abnormal issue was only resolved after I deleted and reconstructed the relevant files and datasets.

If I were to redo this project, I would first figure out the exact meaning of each operational step before allowing AI to intervene in specific tasks. Meanwhile, I would isolate workspace files in advance, so that I can collaborate with AI to troubleshoot errors encountered in the project more reliably.

---

## 12. GenAI Use Declaration

During this course, I used the following AI tools: Google Ai Reply and Gemini.  
They were used for [environment setup / debugging / prompt-based code assistance / language polishing / translation ].  
All AI-assisted outputs included in this report were checked by me and verified against project requirements, documentation, or experimental evidence before being included.

---

## 13. References

1. AAE5303 Course Materials
2. https://github.com/Qian9921/AAE5303_opensplat_demo-
3. https://github.com/pierotofy/OpenSplat
4. https://github.com/sijieaaa/UAVScenes
---

## 14. Appendix (optional)

Null
