---
description: Developer Environment Setup - Playbook
---

# Workspace Setup - Playbook

## Software Prerequisites

* [React Native](https://reactnative.dev)
* NodeJs, NPM , OpenJDK 8
* [Android Studio Dowload](https://developer.android.com/studio)
* [Vysor](https://www.vysor.io/download)
* NDK old Version **20.0.5594570** needed to be compatible. Use command `sdkmanager 'ndk;20.0.5594570'` to switch to ndk **20.0.5594570**. (This command is handy on Mac or Linux)
* Saral SDK (This SDK is embedded in Saral App code base).                                                           Refer  [saral-sdk-source-code-repository.md](../engage/saral-sdk-source-code-repository.md "mention")

### Optional software

* Docker to bring up reference backend as a container ([https://docs.docker.com/desktop/](https://docs.docker.com/desktop/))

## Other tools used

* [Microsoft VoTT(Visual Object Tagging Tool)](https://github.com/microsoft/VoTT)  [VoTT Project Setup Video](https://www.youtube.com/watch?v=uXxE4Sas3uQ)
* [Jupyter Notebook](https://jupyter.org) for transforming VoTT raw json to Saral ROI json. Refer to source repository path **specs\v1\README.md** file for more details. You may consider installing the extension in MS Visual Studio Code.
* PostMan or any other REST client tool to invoke/test Rest APIs.

### Source Code references

> > Open Terminal and clone source code `git clone https://github.com/Sunbird-Saral/Project-Saral.git.`
> >
> > `For latest repo refer` [source-code-repository.md](../engage/source-code-repository.md "mention")

> > Change Directory to `Project-Saral/` folder and switch to release tag as per release notes. `git checkout tags/<tag_name>`

> > `%FRONTEND_FOLDER% = Project-Saral/v1.0/frontend`

> > `%BACKEND_FOLDER% = Project-Saral/v1.0/backend`

## Frontend Setup

* [Setting up the React Native development environment](https://reactnative.dev/docs/environment-setup)  **Note**: Choose `React Native CLI Quick Start` tab for setup instructions.
* Download [**NDK 20.0.5594570**](https://androidsdkoffline.blogspot.com/p/android-ndk-side-by-side-direct-download.html) and extract archive to **%ANDROID\_HOME%**\ndk folder.
* In Android Studio, navigate to `File\Project Structure\SDK Location` and set Android NDK location to **%ANDROID\_HOME%**\ndk\android-ndk-r20 (extracted in the last step).
* Register on [Google Firebase](https://firebase.google.com), add the Saral project on the firebase dashboard and download the corresponding **google-services.json**.
* Place downloaded `google-services.json` under [**%FRONTEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references)/SaralApp/android/app folder.
* Once Vysor and AVD are configured as per the instructions, follow the below steps to bring up the application.
* Open a terminal in [**%FRONTEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references)**/SaralApp** and run "npm i" command.
* cd android && gradlew clean && cd..
* npx react-native run-android
* Make sure backend **BASE\_URL** is configured in [**%FRONTEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references)**/SaralApp/src/configs/config.js** file.
* Successful frontend deployment should show Saral OCR login screen on AVD.

## Backend Setup

* Install node and MongoDB in your local machine.
* After taking pull of project from git, Install npm packages by running `npm i` from [**%BACKEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references).
* Create a subfolder inside backend folder name it as configuration.
* Now create a file in **config\dev.env** and paste below commands

> > `PORT=3000`.

> > `MONGODB_URL=mongodb://localhost:27017/saraldata_dev`.

> > `JWT_SECRET=SARALDATA_NODE`.

* npm run dev
* Successful backend local deployment should show Server is up on port 3000

## Backend DevOps

Dockerfile is available under [**%BACKEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references) folder.

Build docker image using `docker build . -t saral-backend:1.0-latest the` command from [**%BACKEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references) folder in a Terminal.

Docker swarm stack reference file available at [**%BACKEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references)/saralbackend-stack.yml

Docker-compose reference file available at [**%BACKEND\_FOLDER%**](workspace-setup-playbook.md#source-code-references)/docker-compose.yml

## Backend Data Load

* Make sure the backend server is running
*   Command to delete/clean existing data:

    `node ./data/import-data.js --delete`
*   Command to load data from data files in ./backend/data folder.

    `node ./data/import-data.js --import`

## Useful Developer Tools

https://www.npmjs.com/package/react-devtools Note: For the current version of Saral execute `npm i -g react-devtools@"<4.11.0"`
