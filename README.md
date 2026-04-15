# AAE5303 Individual Report on Six Qualitative Indicators

## 1. Metadata

| Item | Details |
|---|---|
| Course | AAE5303 |
| Report type | Individual Report on Six Qualitative Indicators |
| Student name | MAN Chi Lok Louie |
| Student ID | 25001004G |
| Team name / group number | 我們組 (WMZ) |
| Team repo URL | https://github.com/mcllouie/AAE5303_Final-project_--WMZ |
| My role in the team | Visual SLAM and Coordinator |
| My primary module | [VSLAM / ~~3D reconstruction / segmentation / integration~~ / benchmarking / other] |
| Main dataset / scene used | AMtown02 |
| Main tools used | ~~Cursor / Docker~~ / ROS / ORB-SLAM3 / ~~OpenSplat / U-Net~~ / others |
| Main evidence paths | https://github.com/mcllouie/AAE5303-Group_Project-WMZ-VO |
| ~~Commit hash(es) / issue / notebook~~ / slide links | https://mcllouie.github.io/AAE5303-Group_Project-WMZ_Slides/ |
| Declared AI use | Google Ai Replies and Gemini |

---

## 2. Individual Contribution Statement

| Item | Content |
|---|---|
| Team result | Using AMtown02 as the dataset to "play" with the tools |
| My specific role | ORB-SLAM3 |
| My strongest evidence | Using completly MacOS with Apple Silicon to complete the Visual SLAM |
| My main learning focus | How **NOT** to follow pre-defined workflow to obtain the same result |

---

## 3. Project Snapshot

### 3.1 Project goal
To complete the 3 pipelines using the AMtown02 dataset, with the below challenges:
1.  Stubborn guy on using ARM Mac (i.e. no bootcamp) for completing visual SLAM.
2.  TAs had shut down the server **JUST BEFORE REPORT DATE** without prior notification, that computing 3DGS with notebook computers is an issue.
3.  U-Net have given a complete guide, but without hands-on.
\n Anyways, we successfully completed.

### 3.2 Pipeline overview

[3-5 sentences. Briefly explain the overall pipeline involving VO / 3D reconstruction / segmentation.]

### 3.3 My position in the pipeline

[3-5 sentences. Explain where your own work sat in the larger system.]

### 3.4 Reproducibility snapshot
| Item | Details |
|---|---|
| Main environment | Macbook Pro M1Pro Core with MacOS Tahoe (26.2) (Using VM Ubuntu 20.04 via UTM) |
| Key scripts / folders | https://github.com/mcllouie/AAE5303-Group_Project-WMZ-VO/blob/main/scripts/My%20Own%20Steps.md |
| Main evaluation scripts | https://github.com/mcllouie/AAE5303-Group_Project-WMZ-VO/blob/main/scripts/evaluate_vo_accuracy.py |
| Main figures in this report | https://github.com/mcllouie/AAE5303-Group_Project-WMZ-VO/blob/main/figures/AMtown02-4.png |
| What another person should run first | https://github.com/Qian9921/AAE5303_assignment2_orbslam3_demo- |

---

## 4. Six-Indicator Summary Matrix

| Indicator | Before-course (optional) | End-of-course | Main evidence | Main lesson |
|---|---:|---:|---|---|
| 1. Tooling & Reproducible Workflow Readiness |  |  |  |  |
| 2. Prompting Strategy & AI Co-Creation |  |  |  |  |
| 3. Verification, Documentation & Technical Judgment |  |  |  |  |
| 4. Debugging, Iteration & Problem Solving |  |  |  |  |
| 5. Integration & Benchmark-Driven Improvement |  |  |  |  |
| 6. Responsible AI Use, Reflection & Redesign |  |  |  |  |

---

## 5. Indicator 1 - Tooling & Reproducible Workflow Readiness

**Before-course confidence (optional):** `__/5`  
**End-of-course confidence:** `__/5`

### Situation / task
[What setup or workflow task is this section about?]

### What I did
[Describe what you personally configured, ran, organized, or improved.]

### Evidence
- Environment / container / setup command:
- Repo path / script:
- Screenshot / figure:
- Commit / issue / note:
- Reproducibility detail:

### What this shows
[Explain what the evidence shows about your readiness and workflow maturity.]

### Limitation
[What still remains fragile or manual?]

### Next improvement
[One concrete next step.]

---

## 6. Indicator 2 - Prompting Strategy & AI Co-Creation

**Before-course confidence (optional):** `__/5`  
**End-of-course confidence:** `__/5`

### Situation / task
[What AI-assisted task is this section about?]

### What I did
[Describe one prompt that failed or was weak, and how you refined it.]

### Evidence
- Initial prompt:
- Revised prompt:
- Added context / file references:
- Resulting config or code change:
- What the AI still could not solve:

### What this shows
[Explain how your prompting became more effective and why.]

### Limitation
[What is still difficult when working with AI through prompting?]

### Next improvement
[One concrete next step.]

---

## 7. Indicator 3 - Verification, Documentation & Technical Judgment

**Before-course confidence (optional):** `__/5`  
**End-of-course confidence:** `__/5`

### Situation / task
[What technical choice, claim, or AI suggestion did you need to verify or judge?]

### What I did
[Describe how you checked documentation, theory, notes, or alternative settings.]

### Evidence
- Documentation / notes / theory reference:
- Compared alternatives:
- Trade-off identified:
- AI suggestion accepted / rejected:
- Why that decision was justified:

### What this shows
[Explain your reasoning and what engineering judgment this demonstrates.]

### Limitation
[What technical uncertainty remains?]

### Next improvement
[One concrete next step.]

---

## 8. Indicator 4 - Debugging, Iteration & Problem Solving

**Before-course confidence (optional):** `__/5`  
**End-of-course confidence:** `__/5`

### Situation / task
[What failure case or debugging situation is this section about?]

### What I did
[Describe the diagnosis process step by step.]

### Evidence
- Error log / screenshot:
- Suspected cause:
- Change made:
- Before vs after result:
- Repo path / commit:

### What this shows
[Explain what you learned from the debugging and iteration cycle.]

### Limitation
[What debugging problem still takes too long or remains unresolved?]

### Next improvement
[One concrete next step.]

---

## 9. Indicator 5 - Integration & Benchmark-Driven Improvement

**Before-course confidence (optional):** `__/5`  
**End-of-course confidence:** `__/5`

### Situation / task
[What integration or evaluation task is this section about?]

### What I did
[Describe how your work connected to another module or to the full pipeline.]

### Evidence
- Pipeline figure / workflow path:
- Benchmark table / comparison table:
- Metric(s) used:
- Evaluation script / notebook:
- Leaderboard or benchmark link:
- Limitation of the evaluation:

### What this shows
[Explain what the benchmark or comparison actually means.]

### Limitation
[What does this evaluation still fail to prove?]

### Next improvement
[One concrete next step.]

---

## 10. Indicator 6 - Responsible AI Use, Reflection & Redesign

**Before-course confidence (optional):** `__/5`  
**End-of-course confidence:** `__/5`

### Situation / task
[What AI-related risk, limitation, or reflection point is this section about?]

### What I did
[Describe one case where AI output was wrong, risky, incomplete, or misleading, and how you handled it.]

### Evidence
- Incorrect / risky AI output:
- How I detected the problem:
- What I corrected or rejected:
- Authenticity / verification note:
- Redesign priorities:

### What this shows
[Explain what this says about your responsible AI use and engineering maturity.]

### Limitation
[What limitation still remains in your own work or judgment?]

### Next improvement
1. [Priority 1]
2. [Priority 2]
3. [Priority 3]

---

## 11. Overall Growth Summary

[200-300 words. Summarize what the six indicators collectively show about your development in AI-assisted engineering, technical judgment, and personal contribution to the course project.]

---

## 12. GenAI Use Declaration

> During this course, I used the following AI tools: [tool names].  
> They were used for [environment setup / debugging / prompt-based code assistance / language polishing / translation / none].  
> All AI-assisted outputs included in this report were checked by me and verified against project requirements, documentation, or experimental evidence before being included.

---

## 13. References

1. [Course material / repo / documentation / paper]
2. [...]
3. [...]

---

## 14. Appendix (optional)

### Appendix A. Figure gallery
```md
![Figure 1. Pipeline overview](assets/fig1_pipeline.png)
![Figure 2. VO debugging case](assets/fig2_vo_debug.png)
![Figure 3. Reconstruction result](assets/fig3_reconstruction.png)
![Figure 4. Segmentation comparison](assets/fig4_segmentation.png)
```

### Appendix B. Benchmark table
| Experiment | Setting | Metric | Result | Interpretation |
|---|---|---:|---:|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |

### Appendix C. Failure case log
| Case | Symptom | Cause | Fix attempted | Outcome |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |

### Appendix D. Evidence traceability
| Claim in report | Evidence path / commit / notebook / issue |
|---|---|
|  |  |
|  |  |
