OCTA-Net: Split-Based Coarse-to-Fine Vessel Segmentation
Replication of iMED-Lab/OCTA-Net on ROSE-1
Paper: Ma et al., ROSE: A Retinal OCT-Angiography Vessel Segmentation Dataset and New Model, IEEE TMI 2021

Component	Detail
Stage 1 — SCS	Split-based Coarse Segmentation: shared ResNeSt encoder + dual decoder branches (pixel-level thick + centerline-level thin)
Stage 2 — SRS	Split-based Refined Segmentation: ResNeSt encoder-decoder fusing image + both Stage-1 confidence maps
Backbone	ResNeSt blocks (Split-Attention, K=1 cardinal × R=2 radix)
Loss	BCE (both stages)
Dataset	ROSE-1 — 90 train / 27 test, 304×304 px
Categories	SVC (dual-branch), DVC (single-branch), SVC_DVC (dual-branch)
Optimizer	Adam, lr=1e-3, cosine decay
Metrics	Dice, Jaccard, Sensitivity, Specificity, AUC
