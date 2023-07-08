---
sort: 3
---

# TB4 Controller Setup

## TurtleBot 4 Controller Setup

The TurtleBot 4 comes with an included TurtleBot 4 Controller. It is paired in advance with the Raspberry Pi.

If you wish to manually pair a controller, follow these instructions:

- SSH into the TurtleBot 4

```bash
sudo bluetoothctl
```

- The `bluetoothd` CLI interface will start.
- Type `scan on` and press enter.
- Press and hold both the home and share buttons on the TurtleBot 4 controller until the light starts blinking.

<figure class="aligncenter">
    <img src="media/controller.jpg" alt="TurtleBot 4 Controller" style="width: 70%"/>
    <figcaption>Putting the TurtleBot 4 in pair mode</figcaption>
</figure>

- In the CLI look for a *Wireless Controller* device to be found. It will have a MAC address similar to `A0:5A:5C:DF:4D:7F`.
- Copy the MAC address.
- In the CLI enter `trust MAC_ADDRESS`, replacing `MAC_ADDRESS` with the controllers address.
- Then, enter `pair MAC_ADDRESS`.
- Finally, enter `connect MAC_ADDRESS`.
- The CLI should report that the controller has been connected and the light on the controller will turn blue.
- Enter `exit` to exit the CLI.

