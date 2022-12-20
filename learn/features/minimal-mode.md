# Minimal Mode

For non-academic use-cases, there will be no fixed participants like students and hierarchy like class,section etc. So minimal mode is to address these non-academic use-cases where a layout roi can be selected by user,scanned and push the scanned data to backend.

`/schools/login` API reponse has flag `isMinimalMode` to enable minimal mode by default for given organization or school. Refer below sample response for `/schools/login` API for reference.

```
{
    "school": {
        "storeTrainingData": true,
        "name": "Dummy school 3",
        "schoolId": "demouser",
        "state": "gujrat",
        "autoSync": false,
        "autoSyncFrequency": 600000,
        "tags": false,
        "isMinimalMode": true
    }
}
```

![](<../../.gitbook/assets/image (4).png>) ![](<../../.gitbook/assets/image (8).png>) ![](<../../.gitbook/assets/image (1) (1).png>)&#x20;

From `v1.5.6` release and above, a switch option is added to switch between Regular and Minimal mode.&#x20;

![](<../../.gitbook/assets/image (5) (1).png>)![](<../../.gitbook/assets/image (3) (1).png>)

For minimal mode , classsId and sectionId will be defaulted to `0.`Backend data can be differentiated using these field values.
