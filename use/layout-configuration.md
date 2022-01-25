---
description: Layout configuration for Saral App to detect and predict
---

# Layout configuration

Refer [layout-specification.md](../learn/specifications/layout-specification.md "mention")

1. Tools like [MS VoTT](https://github.com/microsoft/VoTT) can be used to tag ROIs with the layout. This will give a raw VoTT Json with ROI coordinates.

2\. Use [Jupyter Notebook](https://jupyter.org) to transform raw VoTT Json to target [layout-specification.md](../learn/specifications/layout-specification.md "mention") json format.

3\. This final layout json should be configured in backend `GET /roi/{examId}` API for each exam to enable the layout.

Refer more details from [Saral App Layout generation and configuring in backend](https://github.com/Sunbird-Saral/Project-Saral/wiki/Saral-App-Layout-generation-and-configuring-in-backend)

Starting from `v1.5.0` release each layout can have threshold minimum width and minimum height configured. This configuration is used by App to detect the sheet only if minimum width and height between dark corner circles is met with scanned sheet/layout. This is to avoid invalid scans which may result in unwanted predictions.

Sample layout with threshould minWidth and minHeight configuration.

```
      "layout": {
          "version": "1.0",
          "name": "HINDI8S13QOMR Exam Sheet Form",
          "threshold": {
              "minWidth" : 500,
              "minHeight": 200
          },            
          "cells": [
              {
                  "cellId": "1",
                  "rois": [
                      {
                          "annotationTags": "ROLLNUMBERID1_1",
                          "extractionMethod": "NUMERIC_CLASSIFICATION",
                          "roiId": "1",
                          "index": 0,
                          "rect": {
                              "top": 151,
                              "left": 54,
                              "bottom": 178,
                              "right": 69
                          }
                      },
```
