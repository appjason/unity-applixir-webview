# Unity AppLixir Webview Project

This project is intended as a simple Unity project to demonstrate AppLixir integrations. This requires a version of Unity of 2020 or newer.

The project is structured so that different branches demonstrate different integration approaches with the AppLixir system.

## Branch: *standalone*
This branch is the basic project with no integration. Pressing the button will result in displaying the time of the click in the result panel. This project is intended to run with a WebGL target, so this target must be set in the Build Settings... before building the project.

## Branch: *webview_webgl*
This branch is integrated with the AppLixir Webview Plugin to display a website with AppLixir configured for display in the game. Pressing the button will display the ad as well as capture AppLixir status to be realyed to the Unity app. The results panel will show the most recent status received from the AppLixir callback. This project is intended to run with a WebGL target, so this target must be set in the Build Settings... before building the project.

### Implementation
This branch was created from the *standalone* branch with the following steps:

1. Copy the Plugins directory from the AppLixir Plugin to the project Assets/ directory.
2. Update the ButtonHandler class to trigger the webview and process the callback status.
3. From within the Unity editor, select the ButtonHandler object and set the Url on the ButtonHandler script to a website with a valid AppLixir website. See the project website folder for an example.
4. Also within the Unity editor, link the ButtonHandler GameObject from the scene to the OnClick handler for the button itself, and set the Function to ButtonHanlder -> PlayVideo.
5. Copy the WebGLTemplates folder from the Plugins directory to the Assets directory.
6. From within the Unity editor, select Project Settings -> Player -> Resolution and Presentation -> WebGL Template -> unity-webview-2020.