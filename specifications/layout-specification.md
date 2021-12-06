---
description: Saral App Layout specification.
---

# Layout specification

This is layout specification for Saral App. Layout ROIs are captured in this format and configured in backend for each exam. Internally Saral App uses this json interface for predicting ROIs.

Checkout Github release tag and refer `Project-Saral/specs/v1/saral-physical-layout-representation-specs.yaml`

1. Cell in the overall layout groups a field as a whole. It is a group of ROI's which will be predicted and grouped together.
2. ROI(Region Of Interest) is an area of interest in the image that will be used to predict/recognize a character/digit/OMR.

