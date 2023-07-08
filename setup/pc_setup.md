---
sort: 1
---

# User PC

These instructions will set up the user PC 

## Ubuntu

To interface with the robot, it is recommended to use a remote PC running the appropriate version of Ubuntu Desktop, with ROS 2 installed.

Required OS: [Ubuntu 22.04](https://releases.ubuntu.com/22.04/)

### Install ROS 2 Humble

Follow [these instructions](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html) to install ROS 2 Humble on your PC.

### Install Turtlebot Desktop

Once ROS 2 is installed, install `turtlebot4_desktop`:

```bash
sudo apt update && sudo apt install ros-humble-turtlebot4-desktop
```


## Terminator Terminal Emulator (Optional)

Terminator is a terminal emulator that allows for multiple GNOME terminals in one window

<figure class="aligncenter">
    <img src="media/terminator-vim-shells-dark-1.png" alt="terminator" style="width: 100%"/>
    <figcaption>Terminator with multiple terminals</figcaption>
</figure>

### Terminator Install

```bash
sudo apt install terminator
```

### Shortcuts
```note
Create more terminals by:

- horizontal split: ```Ctrl-Shift-o```
- vertical split: ```Ctrl-Shift-e```
Shift focus to:

- next terminal: ```Ctrl-Shift-n```
- previous terminal: ```Ctrl-Shift-p```
- New tab: ```Ctrl-Shift-t```
- New window: ```Ctrl-Shift-i```
- Close terminal or tab: ```Ctrl-Shift-w``` or ```right mouse click``` -> Close
- Close window with all it's terminals and tabs: ```Ctrl-Shift-q```
- Reset zoom: ```Ctrl-0```
```

