---
sort: 5
---

# Setup Wifi off campus

## Access Point Mode

```tip
If you are moving your TurtleBot 4 to a new location with a different Wi-Fi network, 
reconfigure the Raspberry Pi to connect to that network beforehand or place it into AP mode. 
Otherwise it will continue trying to connect to your current network.
```
Before leaving campus, SSH into the Raspberry Pi and run the [TurtleBot 4 setup tool](../software/turtlebot4_setup.md#configuration-tools):

```bash
turtlebot4-setup
```

Go to <b>Wi-Fi Setup</b> and select <b>Apply Defaults</b>. Optionally you can set your own SSID and password before saving and applying the new settings.

## Robot

The first step for setting up the TurtleBot 4 off campus is to power it on and connect it to a Wi-Fi network.

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