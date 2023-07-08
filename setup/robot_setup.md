---
sort: 2
---

# Robot Setup

These instructions will set up the robot 

## Robot

The first step for setting up the TurtleBot 4 is to power it on and connect it to your Wi-Fi network.

### Power on the robot

Place the TurtleBot 4 onto its dock. The green LED on the dock will turn on for a few seconds, and the TurtleBot 4 should power on. Allow the robot some time to boot up.

For more details on the robot buttons and indicator lights, visit the [Create&reg;3 Documentation](https://iroboteducation.github.io/create3_docs/hw/face/)

### Connect to the Access Point

On the first boot, the Raspberry Pi will enter Access Point (AP) mode which will allow you to connect to it over Wi-Fi. On your PC, connect to the `Turtlebot4` Wi-Fi network. The password is also `Turtlebot4`.

```note
The TurtleBot 4 AP network is a 5GHz network. Your computer will need to support 5GHz Wi-Fi to connect to the network.
```

### SSH into the Raspberry Pi

Once connected, you can SSH into the Raspberry Pi to configure its Wi-Fi. Open a terminal on your PC and call: 

```bash
ssh ubuntu@10.42.0.1
```

Log in using the password `turtlebot4`.

### Connect the Raspberry Pi to your network

Once logged in, configure the Raspberry Pi to connect to your Wi-Fi network.

```tip
Connect the Raspberry Pi to a 5GHz Wi-Fi network for optimal performance.
```

In your SSH session, run the [TurtleBot 4 setup tool](../software/turtlebot4_setup.md#configuration-tools):

```bash
turtlebot4-setup
```

This will start the TurtleBot 4 setup tool. Navigate to the "Wi-Fi Setup" menu and configure your connection. When you have finished, save and apply the settings.

<figure class="aligncenter">
    <img src="media/wifi_setup.gif" alt="Wi-Fi setup" style="width: 100%"/>
    <figcaption>Wi-Fi Setup using the TurtleBot 4 Setup tool</figcaption>
</figure>

```note
Change your Wi-Fi mode to 'Client' when connecting to an existing network.
```

### Find the new Raspberry Pi IP

Once the Wi-Fi settings are applied, the Raspberry Pi will reboot and connect to your network. DHCP will assign it a new IP address. On the TurtleBot 4, this IP address will be shown at the top of the display. 

<figure class="aligncenter">
    <img src="media/display_ip2.jpg" alt="IP Address" style="transform:rotate(270deg); width: 20%"/>
    <figcaption>Wi-Fi IP address on a TurtleBot 4</figcaption>
</figure>

On your PC, run the following commands:

```bash
source /opt/ros/humble/setup.bash
export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
export ROS_DOMAIN_ID=0
ros2 topic echo /ip
```

You should see the IP address printed out in your terminal periodically.

```bash
$ ros2 topic echo /ip
data: 192.168.28.24
---
data: 192.168.28.24
---
```

```note
If you are unable to find the IP address with the previous methods, try logging into your gateway and looking for a device with host name "ubuntu".
```

Once you have found the IP address, you can now SSH back into the robot with it.

```bash
ssh ubuntu@192.168.28.24
```

### Accessing the Create® 3 webserver

Once you have acquired the Raspberry Pi IP address, you can access the [Create® 3 webserver](https://iroboteducation.github.io/create3_docs/webserver/overview/).

Open a web browser and navigate to your Raspberry Pi IP with the port 8080.

<figure class="aligncenter">
    <img src="media/webserver_rpi.png" alt="Webserver" style="width: 60%"/>
    <figcaption>Accessing the Create® 3 webserver</figcaption>
</figure>

You will be greeted by the Create® 3 webserver home page.

<figure class="aligncenter">
    <img src="media/webserver_home.png" alt="Webserver" style="width: 90%"/>
    <figcaption>Create® 3 webserver home page</figcaption>
</figure>

### Updating the TurtleBot 4

It is recommended to update both the Create® 3 and the Raspberry Pi when you first use it to receive the latest bug fixes and improvements.

#### Create® 3

Check the [Create® 3 software releases](https://iroboteducation.github.io/create3_docs/releases/overview/) to see if a newer firmware version is available. You can check the firmware version of your Create® 3 by visiting the webserver.

```note
The turtlebot 4 for CS 6300/5300 should be running firmware. H.1.2
```

If new firmware is available, download it, then access the [webserver](./basic.md#accessing-the-create-3-webserver). Go to the <b>Update</b> tab, upload the firmware, then update your robot.

#### Raspberry Pi packages

SSH into the Raspberry Pi, then update all packages by calling:

```bash
sudo apt update && sudo apt upgrade
```