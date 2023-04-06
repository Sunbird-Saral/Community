---
description: Layout configuration for Saral App to detect and predict
---

# Layout configuration

Refer [layout-specification.md](../learn/specifications/layout-specification.md "mention")

1.  Capture the printed layout using saral app for tagging.

    1. > Set debug option to true to store the image in android mobile. Modify below java file under /saralsdk and change below highlighted flags to true.

    SaralSDKOpenCVScannerActivity.java

    > > ```
    > >    mTableCornerDetection           = new TableCornerCirclesDetection(true);
    > >    mDetectShaded                   = new DetectShaded(true);
    > > ```

    2. > With the above changes, run the scan on the mobile.
    3. > Use the below command to grab the android level logs and search for 'SrlSDK::CVOps: Saving file:' and 'SrlSDK::DetectShaded: Saving file:'. This will give you path to where the saved images are stored in your android phone.

    `adb logcat`

    4.  > Use the below command to pull the images finally. `adb pull <image path in android phone found in above logs>` example: `adb pull /storage/emulated/0/Android/data/com.saralapp/files/Download/table_4Fg.jpg`



2\. Tools like [MS VoTT](https://github.com/microsoft/VoTT) can be used to tag ROIs with the layout. This will give a raw VoTT Json with ROI coordinates.

3\. Use [Jupyter Notebook](https://jupyter.org) to transform raw VoTT Json to target [layout-specification.md](../learn/specifications/layout-specification.md "mention") json format. Existing layout transformation notebooks can be referred @ `/specs/v1.5/jupyter-notebook` in[ ](../engage/source-code-repository.md)the [Repository](../engage/source-code-repository.md).

4\. This final layout json should be configured in backend `GET /roi/{examId}` API for each exam to enable the layout.

Starting from `v1.5.0` release each layout can have threshold minimum width,minimum height and detectionRadius configured. This configuration is used by App to detect the sheet only if minimum width and height between dark corner circles is met with scanned sheet/layout. This is to avoid invalid scans which may result in unwanted predictions.

Sample layout with threshould minWidth, minHeight and radius(radius of 4 corner dark circles for alignment) configuration.

`threshold\experimentalOMRDetection` flag is used to enable experimental feature to detection OMR filled with pencil or any color pen. This experimental feature will be available from v1.5.6 release or above.



```
  "layout": {
      "version": "1.0",
      "name": "HINDI8S13QOMR Exam Sheet Form",
      "threshold": {
          "minWidth" : 500,
          "minHeight": 200,
          "detectionRadius": 12,
          "experimentalOMRDetection": true
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

**Extraction Methods Supported**

| extractionMethod                        | Description                                                                                                                                                                        |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **NUMERIC\_CLASSIFICATION**             | This extraction method is used for handwritten digits 0 to 9.                                                                                                                      |
| **CELL\_OMR**                           | This extraction method is used for omr detection. Added `experimentalOMRDetection`flag to support OMR filled with pencil,any color ball pens.                                      |
| **BLOCK\_ALPHANUMERIC\_CLASSIFICATION** | This extraction method is used for Alphanumeric detection . For example Address filed can hold block letters with digits. This feature is available from v1.5.6 release and above. |
