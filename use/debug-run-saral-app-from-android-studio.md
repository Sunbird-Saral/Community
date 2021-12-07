---
description: Run or Debug Saral App
---

# Debug/Run Saral App from Android Studio

### Source Code references

> > Open Terminal and clone source code `git clone https://github.com/Sunbird-Saral/Project-Saral.git`
> >
> > For latest repository details , refer: [source-code-repository.md](../engage/source-code-repository.md "mention")

> > Change Directory to `Project-Saral/` folder and switch to release tag as per release notes. `git checkout tags/<tag_name>`

> > `%FRONTEND_FOLDER% or $FRONTEND_FOLDER = Project-Saral/v1.0/frontend`

> > `%BACKEND_FOLDER% or $BACKEND_FOLDER = Project-Saral/v1.0/backend`

Make sure [workspace-setup-playbook.md](workspace-setup-playbook.md "mention") is done. Follow below steps for debugging/running application from Android Studio

1. Open **`$FRONTEND_FOLDER`**`/SaralApp/android folder` from Android Studio.
2. Run `react-native start` command from Terminal in `$FRONTEND_FOLDER/SaralApp` directory.
3. Run `adb reverse tcp:8081 tcp:8081` from another terminal
4. Now click on the `Run` or `Debug` button from Android studio.
5. When you are debugging, have debug breakpoints in android code as needed for troubleshooting.
