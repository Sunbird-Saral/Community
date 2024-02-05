---
description: Saral supports handling secure storage of PII data by providing configurable field encryption of PII schema with different data security levels like encryption, encryption+masking, encryption+hashing.
---

# Configurable field encryption of collection schema(ex: admissions) with different levels

Saral App supports enabling PII data encryption from `v1.6.3` release which is added to admissions usecase.

The admissions record captures sensitive PII data of a student. It is necessary to manage data security.

Saral reference backend provides data encryption feature for Admissions record which can be configured at field level(each and every column/key in admissions record). 
Currently supports 6 different levels of encryption termed as:
* ENCRYPTANDHASH - does encryption of data first and then hashing of encrypted data for added security
* ENCRYPT - does encryption of data only
* HASH - does hashing of data only
* MASK - does masking of data only
* ENCRYPTANDMASK - does encryption of data first and then masking of encrypted data for added security
* ENCRYPTARRAY - does encryption of array type of data

Saral reference solution uses below algorithms for data security
```
Encryption: AES 256
Hashing: SHA 256
```

Data encryption can be configured under branding for a specific state. A new key named “encryptionSchemas” is added to brands schema which holds an object containing info about field level encryption enabling/disabling with the type of encryption. Refer to [configurable-branding.md](./configurable-branding.md) for more details.

By default the reference solution implements admissions record encryption as shown in below sample, which is added to default branding record and saved under brand collection in DB.

```
"encryptionSchemas": {
      "admissions": {
       "studentAadharNumber": "ENCRYPTANDMASK",
       "studentFirstname": "ENCRYPT",
       "studentSurname": "ENCRYPT",
       "studentDateOfBirth": "ENCRYPT",
       "studentAddress": "ENCRYPT",
       "studentBlock": "ENCRYPT",
       "studentDistrict": "ENCRYPT",
       "guardianFirstname": "ENCRYPT",
       "guardianSurname": "ENCRYPT",
       "fatherName": "ENCRYPT",
       "fatherContactDetails_phone1": "ENCRYPTANDMASK",
       "fatherContactDetails_phone2": "ENCRYPTANDMASK",
       "motherName": "ENCRYPT",
       "motherContactDetails_phone1": "ENCRYPTANDMASK",
       "motherContactDetails_phone2": "ENCRYPTANDMASK",
       "rollNumber": "ENCRYPTANDHASH",
       "addressOnRationCard_address": "ENCRYPTANDHASH",
       "addressOnRationCard_ward": "ENCRYPTANDHASH",
       "addressOnRationCard_block": "ENCRYPTANDHASH",
       "addressOnRationCard_district": "ENCRYPTANDHASH",
       "predictionInfo": {
          "trainingData": "ENCRYPTARRAY"
       }
      }
    }
```
Reference solution also allows state/adaptors to override the above encryption config by defining a similar structure as shown above in state specific branding.

**Refer to this documentation to know more about additional guidelines that can be implemented to secure data [Data Security guidelines for Saral - Admissions use case](https://docs.google.com/document/d/1tH5B3bZF57YoVUDJhVb_ra7Xti7I_DENof0KClZJlRM/edit?usp=sharing)**
