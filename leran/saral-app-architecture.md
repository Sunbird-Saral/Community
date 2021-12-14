---
description: Application Architecture of Saral App
---

# Application Architecture

**Overall Architecture**

![](<../.gitbook/assets/Saral v1.0 Architecture.png>)

* [ ] Refer [`CQube`](https://cqube.sunbird.org)for documentation
* [ ] Saral uses [Tensorflow Lite](https://www.tensorflow.org/lite) AI/ML model embedded within Android Application for predicting Handwritten digits.
* [ ] Each layout is configurable in the backend as JSON. Refer [layout-specification.md](specifications/layout-specification.md "mention") and[layout-configuration.md](../use/layout-configuration.md "mention") for more details.



**Saral SDK and Application Architecture**

![](<../.gitbook/assets/saral\_sdk\_app\_arch-Saral SDK.png>)

* [ ] ****[**Saral SDK**](../engage/saral-sdk-source-code-repository.md) is an Android and React Native Software Development kit with core logic to predict  handwritten digits and OMR bubbles.
* [ ] ****[**Saral SDK**](../engage/saral-sdk-source-code-repository.md) accepts layout JSON as input and enriches the JSON with predictions and sends back the response. Refer [layout-specification.md](specifications/layout-specification.md "mention")
* [ ] ****[**Saral SDK**](../engage/saral-sdk-source-code-repository.md) component can be reused for Android and React Native App development with handwritten digits and OMR bubbles prediction capabilities.
