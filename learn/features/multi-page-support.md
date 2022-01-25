# Multi-Page support

Saral App supports multi-page layouts from `v1.5.0` release. [layout-specification.md](../specifications/layout-specification.md "mention") supports adding pages element to input number of pages configured for given layout and assign `page`  at each cell level. if a `page` element is not present in a cell , cell is applicable for all the pages. This support is added to `SaraSDK`.&#x20;

Example below shows layout with 3 pages where each question cells assigned with page number.&#x20;

```
      "layout": {
          "version": "1.0",
          "name": "ANY1S15QMULTIPAGE Exam Sheet Form",
          "pages": "3",
          "cells": [
              {
                  "cellId": "2",
                  "page": "1",
                  "rois": [
                      {
                          "annotationTags": "QUESTION1_0",
                          "extractionMethod": "CELL_OMR",
                          "roiId": "8",
                          "index": 0,
                          "rect": {
                              "top": 165,
                              "left": 275,
                              "bottom": 194,
                              "right": 300
                          }
                      },
```
