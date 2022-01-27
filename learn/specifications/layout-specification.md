---
description: Saral App Layout specification.
---

# Layout specification

This is the layout specification for Saral App. Layout ROIs are captured in this format and configured in the backend for each exam. Internally Saral App uses this json interface for predicting ROIs.

Checkout Github release tag and refer&#x20;

Release v1.5 refer

`Project-Saral/specs/v1.5/saral-physical-layout-representation-specs.yaml`

Release v1.0 refer

`Project-Saral/specs/v1/saral-physical-layout-representation-specs.yaml`

![](../../.gitbook/assets/odisha\_layout\_marking.jpg)

1. The **Cell** is a field-level grouping of ROIs. It is a group of ROI's which will be predicted and grouped together. For example, Student ID may have 13 ROI's(for 13 digits) and they are all grouped under one cell to represent the student ID field as a whole.&#x20;
2. ROI(Region Of Interest) is an area of interest in the image that will be used as input to predict/recognize a character/digit/OMR.

`Refer` [source-code-repository.md](../../engage/source-code-repository.md "mention")
