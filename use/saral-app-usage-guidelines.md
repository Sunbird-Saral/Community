---
description: Guidelines how to use the Saral App
---

# Saral App Usage Guidelines

1. Make sure scanning with Mobile/Tab happens in Landscape mode(shown in **Figure#1** below). ![](../.gitbook/assets/landscape\_mode1.jpeg)(**Figure#1**)

2\. Printed layouts have 4 dark circles on the corner of the sheets(shown in **Figure#2**). Make sure these are printed with a proper quality printer. Avoid xerox copies of these layouts.

![](../.gitbook/assets/layout\_screenshot.jpg)(**Figure#2**)

3\. Make sure the user is holding the device is in a stable state until the predictions appear on the App screen.

4\. For OMR sheets make sure bubbles are filled using a blue or black ball pen without any gaps for proper detection.

5\. Minimum width and height between dark circles for each layout can be configured in the backend layout json as threshold. This will have addtional check to layout detection logic. Only if minimum width and height requirement configured in layout is met , layout detection succeeds. App shows warining message as show in below screenshot if minumum height and width is not met. This feature is available from `v1.5.0` release

![](../.gitbook/assets/Screenshot\_20220125-124123\_SaralApp.jpg)

(**Figure#3)** Warning when threshould is configured in layout json and criteria is not met.

6\. Succesful scan from Saral App will have indications shown in below Figures.

![](../.gitbook/assets/scan\_success\_1.jpeg)

(**Figure#4**) Detected the layout to be processed for detection.



![](<../.gitbook/assets/scan\_success\_2.jpeg (1).jpeg>)

(**Figure#5**) Processing detected layout for predictions. Make sure the "Please wait, scanning is in progress !!" message in blue colour is in the same direction as the layout. If both of them are  oriented in a different direction then its the wrong way to scan.
