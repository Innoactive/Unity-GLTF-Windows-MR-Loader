# VRTK-Windows-MR-Extension
Extension for Virtual Reality Toolkit to include **Windows Mixed Reality Controller** visualization.

## How To Use
Simply add this repository to your VRTK Unity project which includes the current [development branch](https://github.com/Innoactive/IA-unity-VR-toolkit-VRTK/tree/feature/windows-mixed-reality-refactored-rebased) of **VRTK 3.3.0 alpha with native Windows Mixed Reality support**. It's recommended to add this repository as a submodule outside of the VRTK (submodule) folder.

**Important:** Make sure to move the folder `UWP` and all it's content to the top level of your Unity project (next to `Assets`).

<!--Simply add this repository to your project that also includes [**VRTK**](https://github.com/thestonefox/VRTK).-->

Example project structure:
```
+-- Assets
|	+-- Extensions
|	|   +-- VRTK
|	|   +-- VRTK-Windows-MR-Extension
|	+-- Folder_1
|	+-- Folder_2
|	...
+-- UWP
```
**NOTE:** VRTK will check for a script included in this repository and adds a Scripting Predefine Symbol (_VRTK_DEFINE_WINDOWSMR_CONTROLLER_VISUALIZATION_) if found. If you encounter unexpected behaviour make sure the Predefine Symbol is added in the Player Settings.

If missing, add the `MotionControllerVisualization` component to the `ControllerManager` which is part of the WindowsMR SDKSetup.

## What is included

- Functionality to visualize **Windows Mixed Reality Motion Controllers** in Editor and Build
- [**glTF**](https://github.com/KhronosGroup/UnityGLTF) which is used to load models at runtime
- This repository mostly includes altered components from [**Microsoft Mixed Reality Toolkit**](https://github.com/Microsoft/MixedRealityToolkit-Unity) to fit **VRTK**

## Why is this not included in VRTK
This repository holds a lot of Windows specific code which people who want to use VRTK may not ever use, e.g. when they just want to use Oculus or SteamVR. An SDK in VRTK is always dependent on a vendor SDK package to be installed, but that's about it. For Oculus models to show up you actually need to also import Oculus Avatar, but VRTK works fine without Avatar being imported. The same is done with this repository since there is no native solution by Microsoft.

In a future iteration this repository will also be provided as a unity package.