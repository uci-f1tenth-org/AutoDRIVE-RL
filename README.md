# Overview
This repo contains the code to train an RL model in the AutoDRIVE Simulator with DreamerV3!!
# Installation
## Cloning repo
First, recursively clone this repository to get all git submodules:
```bash
git clone --recursive https://github.com/AlistairKeiller/AutoDRIVE-RL
```
## Autodrive
Install the [Unity Hub](https://docs.unity3d.com/hub/manual/InstallHub.html). From within the hub, [install Unity version](https://learn.unity.com/tutorial/install-the-unity-hub-and-editor#662942dfedbc2a0315217028) 2022.3.52f1. Your Unity Hub should look like this:
![Unity Hub](<images/Unity Hub.png>)

Then open `./AutoDRIVE` in a Unity Editor using the Unity Hub (we will be using the Unity Editor with AutoDRIVE open as our simulator).

Finally, open the `F1TENTH - MARL` scene by searching the project assets. Then delete the `F1TENTH 2` car asset from the assets folder (this approach currently supports at most one brain in the scene, so you need to delete the second car asset for the time being). At the end, your editor should look like this:

![Unity Editor With MARL Opened](<images/Unity Editor With MARL Opened.png>)
## SheepRL
In order to run sheeprl, first install `uv` if you haven't already (note this is our package manager / virtual environment creator, so please don't use `python -m venv` or `pip` in tandem. You are free to use those instead if you prefer, but they won't be officially supported):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
Now run the RL environment:
```bash
uv run sheeprl/sheeprl.py exp=dreamer_v3_autodrive env=autodrive
```
It will prompt you to "Start training by pressing the Play button in the Unity Editor" twice (the first time is for configuration, the second time is for training). Now you should have DreamerV3 running in the AutoDRIVE simulator!

## Ros setup

```bash
source /opt/ros/humble/setup.bash
colcon build
source install/setup.bash
```
Then you can run
```bash
ros2 launch autodrive_f1tenth simulator_bringup_headless.launch.py
```
for headless,
```bash
ros2 launch autodrive_f1tenth simulator_bringup_rviz.launch.py
```
for rvis, and
```bash
ros2 run autodrive_f1tenth teleop_keyboard
```
for teleop.