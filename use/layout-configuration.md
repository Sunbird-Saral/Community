---
description: Layout configuration for Saral App to detect and predict
---

# Layout configuration

Refer [layout-specification.md](../leran/specifications/layout-specification.md "mention")

1. Tools like [MS VoTT](https://github.com/microsoft/VoTT) can be used to tag ROIs with the layout. This will give a raw VoTT Json with ROI coordinates.

2\. Use [Jupyter Notebook](https://jupyter.org) to transform raw VoTT Json to target [layout-specification.md](../leran/specifications/layout-specification.md "mention") json format.

3\. This final layout json should be configured in backend `GET /roi/{examId}` API for each exam to enable the layout.

Refer more details from [Saral App Layout generation and configuring in backend](https://github.com/Sunbird-Saral/Project-Saral/wiki/Saral-App-Layout-generation-and-configuring-in-backend)
