---
sort: 4
---

# Access Mode

## Access Point Mode

Placing the Raspberry Pi into Access Point mode can be useful when using the robot in an area without Wi-Fi connection.

SSH into the Raspberry Pi and run the [TurtleBot 4 setup tool](../software/turtlebot4_setup.md#configuration-tools):

```bash
turtlebot4-setup
```

Go to <b>Wi-Fi Setup</b> and select <b>Apply Defaults</b>. Optionally you can set your own SSID and password before saving and applying the new settings.

```tip
If you are moving your TurtleBot 4 to a new location with a different Wi-Fi network, 
reconfigure the Raspberry Pi to connect to that network beforehand or place it into AP mode. 
Otherwise it will continue trying to connect to your current network.
```
