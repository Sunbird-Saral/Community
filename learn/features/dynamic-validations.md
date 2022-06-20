# Dynamic Validations

Saral App supports dynamic validation feature. As this application will be used by different educational boards , this feature will avoid maintaining different frontend source code to customise validations. This feature is available from `v1.5.1` release.

The validations can be configured in the ROI Layouts JSON in backend using regular expressions and failure messages.&#x20;

Refer [layout-specification.md](../specifications/layout-specification.md "mention") and [layout-configuration.md](../../use/layout-configuration.md "mention")for details about ROI Layout configuration.

Dynamic validation will come from backend with regular expression, and dynamic validation is used at cell level if validation is not available at cell level then in that case result validation will be used which is used as global result validation and it will also come from backend.

Result validation(This is global result validation irrespective of cell level)&#x20;

`"resultValidation": { "validate": { "regExp": "[0-1]", "errorMsg": "Omr result should be 1 or 0" } }`

Cell level validation&#x20;

`"validate": { "regExp": "[0-1]", "errorMsg": "Omr result should be 1 or 0" }`

`"validate": { "regExp": "[0-5]", "errorMsg": "Omr result should be 0 to 5" }`
