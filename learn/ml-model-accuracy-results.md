# ML Model Accuracy/Results

## Handwritten Alphanumeric model

#### Iteration 1:

| Model details                  | Dataset          | Accuracy achieved |
| ------------------------------ | ---------------- | ----------------- |
| Model trained and inference on | Existing dataset | 99.80%            |
| Model inference on             | NIST dataset     | 62.70%            |
| Average across all datasets    | -                | 81.25%            |

**Reasoning** - As model is trained on the existing dataset, doesn't perform good on NIST dataset

#### Iteration 2:

| Model details    | Dataset                                    | Accuracy achieved |
| ---------------- | ------------------------------------------ | ----------------- |
| Model trained on | Existing dataset + NIST misclassifications | 83.30%            |

**Reasoning** - After training the model on NIST misclassifications, improvement in accuracy

#### Iteration 3:

| Model details    | Dataset                                    | Accuracy achieved |
| ---------------- | ------------------------------------------ | ----------------- |
| Model trained on | Existing dataset + NIST misclassifications | 93.90%            |

**Reasoning** - After training the model on NIST misclassifications as per previous checkpoint, improvement in accuracy

#### Iteration 4:

| Model details    | Dataset                                                                  | Accuracy achieved |
| ---------------- | ------------------------------------------------------------------------ | ----------------- |
| Model trained on | Existing dataset + manually collected dataset from sheets (\~1K samples) | 93.90%            |

**Reasoning** - Training the model upon previous checkpoint and adding manually collected data, improvement in accuracy

## Handwritten Digits model

#### Iteration 1:

| Model details                  | Dataset                                 | Accuracy achieved |
| ------------------------------ | --------------------------------------- | ----------------- |
| Model trained and inference on | Existing dataset                        | 99.90%            |
| Model inference on             | NIST dataset                            | 60.00%            |
| Model inference on             | Obtained production data (\~50 samples) | 97.70%            |
| Average across all datasets    | -                                       | 85.80%            |

**Reasoning** - As model is trained on the existing dataset, doesn't perform good on NIST dataset

#### Iteration 2:

| Model details    | Dataset                                   | Accuracy achieved |
| ---------------- | ----------------------------------------- | ----------------- |
| Model trained on | Existing dataset + NIST misclasifications | 96.40%            |

**Reasoning** - After training the model on NIST misclassifications, improvement in accuracy

#### Iteration 3:

| Model details    | Dataset                                                                       | Accuracy achieved |
| ---------------- | ----------------------------------------------------------------------------- | ----------------- |
| Model trained on | Existing dataset + NIST misclasifications + production dataset (\~50 samples) | 99.70%            |

**Reasoning**: After training the model on NIST misclassifications and production dataset, improvement in accuracy

#### Iteration 4:

| Model details    | Dataset                                                                                             | Accuracy achieved |
| ---------------- | --------------------------------------------------------------------------------------------------- | ----------------- |
| Model trained on | Existing dataset + NIST misclasifications + manually collected dataset from sheets (\~8.6k samples) | 98.30%            |

**Reasoning**: As averaging upon a large production dataset, the accuracy slightly dips as compared to iteration 3

## Sample dataset images

#### Existing dataset

**Handwritten alphanumeric**

![0a56f9eb1545428f8d9aea0665b7c460](https://user-images.githubusercontent.com/104554231/229728834-a7681ad6-bd4f-488b-8e65-62052d418a02.jpg) ![0b0de241b7e64e918fada2f896efdf24](https://user-images.githubusercontent.com/104554231/229728866-6c7b8765-3cb9-4acb-b99e-6c3b1e3cf4bf.jpg) ![00b6ef24818b4323b4ada81ad433af67](https://user-images.githubusercontent.com/104554231/229728911-c39fd804-f2ec-4dfa-9075-9d64e7c84fa1.jpg) ![0ac132e3693c47ccb2fe40fb465ba060](https://user-images.githubusercontent.com/104554231/229728951-b2815ce4-f177-40ca-8192-c6eb2778c04e.jpg) ![0aeaa24048ff4c5d8312d37671c6e08e](https://user-images.githubusercontent.com/104554231/229728980-9a5a1fbb-7644-49c8-b2fa-57a974a69e0e.jpg) ![0b7f1f188faf453b83704a069791f28f](https://user-images.githubusercontent.com/104554231/229729018-546e5cb8-7cd1-40ee-b92a-24660bd7eb50.jpg) ![0bd15fe615db458781bce7dc32a926b5](https://user-images.githubusercontent.com/104554231/229729053-75efe9dd-7769-4595-8dce-faac1839bd8d.jpg) ![0adb585eae814b62a56695650cac0666](https://user-images.githubusercontent.com/104554231/229729111-a142f1a1-22bc-43ac-9a04-11f77fabe794.jpg) ![0b0ffa9c3dcf497c8da259d391f5f159](https://user-images.githubusercontent.com/104554231/229729165-b4060026-56b8-4b1c-ace2-f6d1d17e403e.jpg) ![0b2c4c540a7247629e1dd7a9abd59962](https://user-images.githubusercontent.com/104554231/229729203-2e311e0d-e77a-4076-a338-be7c2ad58e48.jpg)

**Handwritten digits**

![0b1a2b29b0904989a3f6df3a13b93d89](https://user-images.githubusercontent.com/104554231/229729405-0ac01786-e0b8-4724-90c9-f94b7da24581.jpg) ![0abb9b222a1142bdaabd30b6742ca8b2](https://user-images.githubusercontent.com/104554231/229729424-baee18ff-46b5-4612-8fd2-0f12bda1d658.jpg) ![0afd4ac792f14b8185d54cb9d0937b3e](https://user-images.githubusercontent.com/104554231/229729467-fea6c80e-f714-4e8b-882e-50f554338779.jpg) ![0ac2ad40-7af8-44b4-9829-284a2b33416c\_printed](https://user-images.githubusercontent.com/104554231/229729496-2c3eb05b-3f22-44b6-9c81-7fc0d7c9d4c9.jpg) ![00af4fd32ddc42efbfb1222725599ecf](https://user-images.githubusercontent.com/104554231/229729524-9d6f9b28-6689-452f-a6fe-53d2a28c04ee.jpg) ![0aa35cc5-4472-455d-a575-7167c15df849\_generated](https://user-images.githubusercontent.com/104554231/229729574-0ce01249-f857-49b5-8c68-bebe392fc562.jpg) ![0a8986b29e804002a3136ddf110f3638](https://user-images.githubusercontent.com/104554231/229729638-552ef113-a3c6-447f-abe7-c6c5fdd46ce2.jpg) ![0a1d909f2f2847b795ac40cefa452c3e](https://user-images.githubusercontent.com/104554231/229729688-4fcec72c-fc81-4be6-9800-b725b69e4f1f.jpg) ![0\_\_0040c46a-eae7-4219-bffb-7dd418ad9ffb\_up\_govt](https://user-images.githubusercontent.com/104554231/229729726-92b53d2b-bb33-4e1a-8324-25b880ad56ff.jpg) ![00c9de07f7b640d083680a5c21661a8b](https://user-images.githubusercontent.com/104554231/229729771-5b7fd3fd-404b-45c5-bcc4-6e16b21ad20d.jpg)

#### NIST dataset

**Handwritten alphanumeric**

![hsf\_0\_00017](https://user-images.githubusercontent.com/104554231/229730299-9d3eb74d-6824-4f05-bfbc-a7ef6a2c9257.png) ![hsf\_0\_00043](https://user-images.githubusercontent.com/104554231/229730351-eef9aae8-492f-4847-8a84-23bc733576e0.png) ![hsf\_0\_00017](https://user-images.githubusercontent.com/104554231/229730382-02997f2e-e4c1-4c0f-9e4d-e2793b2a4d90.png) ![hsf\_0\_00020](https://user-images.githubusercontent.com/104554231/229730415-a14cc5e9-5f27-48ae-b6e4-de00adc4c0af.png) ![hsf\_0\_00010](https://user-images.githubusercontent.com/104554231/229730469-ad835be3-79dc-4711-9b24-fed9f2b6eb43.png) ![hsf\_0\_00017](https://user-images.githubusercontent.com/104554231/229730508-87491dc2-d789-499d-bc50-4cfe564101c6.png) ![hsf\_0\_00020](https://user-images.githubusercontent.com/104554231/229730556-4d3d3834-4c23-4359-8e0f-2832a5cf89be.png) ![hsf\_0\_00008](https://user-images.githubusercontent.com/104554231/229730590-e064eb19-020c-4285-ada4-b074f22bd787.png) ![hsf\_0\_00025](https://user-images.githubusercontent.com/104554231/229730636-2e7131fd-b6c4-4784-a01c-fdbc3afd49d6.png) ![hsf\_0\_00010](https://user-images.githubusercontent.com/104554231/229730689-a3def9d9-0462-4c80-ad81-1ac4659f2ed4.png)

**Handwritten digits**

![hsf\_0\_00015](https://user-images.githubusercontent.com/104554231/229730804-f4cf3b8a-1676-4c59-aafe-40ad101701c2.png) ![hsf\_0\_00010](https://user-images.githubusercontent.com/104554231/229730833-fdd7070e-b2ad-4a93-9aec-8be4dd8ed0d1.png) ![hsf\_0\_00017](https://user-images.githubusercontent.com/104554231/229730849-48c5ae43-e46a-4a77-8a16-898b1b74d21f.png) ![hsf\_0\_00009](https://user-images.githubusercontent.com/104554231/229730879-b3eeab31-185e-488d-ad11-5d7f36e0b64f.png) ![hsf\_0\_00117](https://user-images.githubusercontent.com/104554231/229730925-14c9b2b2-385f-4f4d-900c-22ea831ca552.png) ![hsf\_0\_00009](https://user-images.githubusercontent.com/104554231/229730959-b5e501af-eda4-43b4-84d9-5aad992ba148.png) ![hsf\_0\_00012](https://user-images.githubusercontent.com/104554231/229730998-b65b66fb-99a6-450d-ac69-a983bc3f4395.png) ![hsf\_0\_00019](https://user-images.githubusercontent.com/104554231/229731041-a4a7dae7-3829-402b-960a-ffc75569dcdf.png) ![hsf\_0\_00009](https://user-images.githubusercontent.com/104554231/229731085-130d9b21-bae1-4e90-b328-26e70a8c498a.png) ![hsf\_0\_00013](https://user-images.githubusercontent.com/104554231/229731151-6a285899-bad4-43a2-87a7-863809a69afb.png)

#### Manually collected

**Handwritten alphanumeric**

![img014-032](https://user-images.githubusercontent.com/104554231/229731461-842be1d2-7f05-4b46-a9a9-7c33773ae1e6.jpg) ![img015-044](https://user-images.githubusercontent.com/104554231/229731590-65a8bf93-cce0-404d-a106-75ce0e9be53e.jpg) ![img016-045](https://user-images.githubusercontent.com/104554231/229731652-9e0980c2-7560-4267-a5cf-3fb09fae0b73.jpg) ![img023-039](https://user-images.githubusercontent.com/104554231/229731690-82841cf8-9bc6-4bd8-8ee8-8f0efbbc7d09.jpg) ![img026-001](https://user-images.githubusercontent.com/104554231/229731742-997c7dfd-bdd4-4776-bffb-5847c189b68e.jpg) ![img029-045](https://user-images.githubusercontent.com/104554231/229731791-d463c5fb-1f2f-490d-9f37-248146334d52.jpg) ![img013-040](https://user-images.githubusercontent.com/104554231/229731828-c6bc84e5-6f45-4182-aa67-b7abb6972212.jpg) ![img032-053](https://user-images.githubusercontent.com/104554231/229731876-b87e2d75-6e3e-4900-9701-9d8a071b0904.jpg) ![img034-055](https://user-images.githubusercontent.com/104554231/229731969-69e1e111-b13d-4f51-83b3-ee89dd384f02.jpg) ![img011-033](https://user-images.githubusercontent.com/104554231/229732030-4c5265ed-c320-481d-925b-1bd42eda74d8.jpg)

**Handwritten digits**

![33665](https://user-images.githubusercontent.com/104554231/229732166-dfb1e6f4-79a4-46dd-aa86-5c1eba6c6ba8.png) ![33679](https://user-images.githubusercontent.com/104554231/229732203-f38acb46-7212-4cc2-9718-15af59ff4c84.png) ![33758](https://user-images.githubusercontent.com/104554231/229732228-97da7a10-36b3-4c27-bdb4-38ec83bd112a.png) ![33745](https://user-images.githubusercontent.com/104554231/229732258-a04a6986-902c-471f-920a-0ca86639cca6.png) ![33650](https://user-images.githubusercontent.com/104554231/229732280-f7ef258a-3445-43f3-aa20-7ae8b57c1919.png) ![33753](https://user-images.githubusercontent.com/104554231/229732313-6e6841df-6024-4d68-affa-b50fea353fea.png) ![31372](https://user-images.githubusercontent.com/104554231/229732377-385301ff-6d24-4f76-b111-45b37caf7596.png) ![33362](https://user-images.githubusercontent.com/104554231/229732444-23a8ef8a-0dd1-4789-846f-d675f2b75e9b.png) ![31075](https://user-images.githubusercontent.com/104554231/229732556-37b99ce5-4e90-4e62-8c69-c6162cdc789d.png) ![31065](https://user-images.githubusercontent.com/104554231/229732609-20634d4f-a4eb-43e2-b03f-a7ac0425dc02.png)

#### Some unhandled misclassifications

![18103](https://user-images.githubusercontent.com/104554231/229733361-616dc17a-9c84-4d3f-9046-8790fc4009b6.png) ![28926](https://user-images.githubusercontent.com/104554231/229733480-2d30388b-1653-4778-bda0-4949899ea6f2.png) ![607](https://user-images.githubusercontent.com/104554231/229733515-47e25ccf-8448-49bd-8456-b65acf300dd6.png) ![30658](https://user-images.githubusercontent.com/104554231/229733543-1604df90-5953-4b3b-9312-f3759e924ca6.png) ![402](https://user-images.githubusercontent.com/104554231/229733591-6b75ac87-e14c-4c13-9035-3fcd8f510e69.png) ![32358](https://user-images.githubusercontent.com/104554231/229733649-ac697ba2-7c1a-4e56-bceb-dff83a5f684e.png) ![24141](https://user-images.githubusercontent.com/104554231/229733812-ec789498-8f13-4374-8f1d-c9aaf1f8a0ed.png) ![30838](https://user-images.githubusercontent.com/104554231/229733864-cee75918-1478-4a2f-8443-dd7fe3585430.png) ![24158](https://user-images.githubusercontent.com/104554231/229733937-99a629bd-a961-497d-af0b-8e5c87f4f97f.png) ![32225](https://user-images.githubusercontent.com/104554231/229733986-c1bf94b8-8efe-438f-a737-6d4c99725d48.png)

**Reasoning**: Generally occurs if the digits are written in corners of the cell
