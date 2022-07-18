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
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MmQxNDk4NzNlNzYwYTAwM2VkZTNiMGEiLCJpYXQiOjE2NTgxMjE2NjV9.aycmUH6GjaTBP1HinzL0qrCzU2acLKKGHOmxp5XDPGg",
    "classes": [
        {
            "sections": [
                {
                    "section": "D"
                },
                {
                    "section": "B"
                },
                {
                    "section": "C"
                }
            ],
            "classId": "3",
            "className": "Class-3"
        },
        {
            "sections": [
                {
                    "section": "D"
                },
                {
                    "section": "B"
                },
                {
                    "section": "C"
                }
            ],
            "classId": "4",
            "className": "Class-4"
        },
        {
            "sections": [
                {
                    "section": "D"
                },
                {
                    "section": "B"
                },
                {
                    "section": "C"
                },
                {
                    "section": "A"
                }
            ],
            "classId": "5",
            "className": "Class-5"
        },
        {
            "sections": [
                {
                    "section": "D"
                },
                {
                    "section": "B"
                },
                {
                    "section": "C"
                }
            ],
            "classId": "6",
            "className": "Class-6"
        },
        {
            "sections": [
                {
                    "section": "D"
                },
                {
                    "section": "B"
                },
                {
                    "section": "C"
                }
            ],
            "classId": "7",
            "className": "Class-7"
        },
        {
            "sections": [
                {
                    "section": "A"
                },
                {
                    "section": "B"
                }
            ],
            "classId": "8",
            "className": "Class-8"
        }
    ]
}
```

![](<../../.gitbook/assets/image (4).png>) ![](../../.gitbook/assets/image.png) ![](<../../.gitbook/assets/image (1).png>)&#x20;

