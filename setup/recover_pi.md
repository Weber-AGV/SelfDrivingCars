---
sort: 5
---

# Recover Raspberry Pi

If you entered incorrect Wi-Fi credentials or your Wi-Fi network is down, you will not be able to access the Raspberry Pi over Wi-Fi. To recover from this, you can connect directly to the Raspberry Pi using an ethernet cable. You may need a USB to Ethernet adapter for your PC.

<figure class="aligncenter">
    <img src="media/ethernet.jpg" alt="Ethernet connection" style="width: 80%;"/>
    <figcaption>Connecting to the TurtleBot 4 over Ethernet</figcaption>
</figure>

The Raspberry Pi uses a static IP address for the ethernet interface, `192.168.185.3`. You will need to configure your wired connection to use the same subnet:

- Go to your wired connection settings.
- Set your IPv4 Method to `Manual` and set your static IP. The IP address cannot be the same as the Raspberry Pi.

<figure class="aligncenter">
    <img src="media/static_ip.png" alt="Setting IP" style="width: 70%;"/>
    <figcaption>Configure your PC's wired IP</figcaption>
</figure>

- Click 'Apply'

You can now go to your terminal and SSH into the robot by typing:

```bash
ssh ubuntu@192.168.185.3
```

## Install latest Raspberry Pi image

```warning
Installing a new image on the Raspberry Pi will delete any changes you may have made. Save your changes externally before proceeding.
```

Find the latest TurtleBot 4 Raspberry Pi images at <http://download.ros.org/downloads/turtlebot4/>.

- Download the latest image extract it. 
- Power off your robot and then remove the microSD card from the Raspberry Pi.
- Insert the microSD card into your PC. You may need an adapter.
- Install the imaging tool `dcfldd`

```bash
sudo apt install dcfldd
```
- Identify your SD card

```bash
sudo fdisk -l
```

- The SD card should have a name like `/dev/mmcblk0` or `/dev/sda`.

- If you wish to backup your current image, do so now:

```bash
sudo dd if=/dev/<SD_NAME> of=<IMAGE_PATH> bs=1M
```

```note
SD_NAME is the device name (`mmcblk0`, `sda`, etc.).

IMAGE_PATH is the path to where you want the image saved -- e.g., `~/turtlebot4_images/backup_image`.
```

- Get the SD flash script from `turtlebot4_setup` and flash the SD card:

```bash
wget https://raw.githubusercontent.com/turtlebot/turtlebot4_setup/humble/scripts/sd_flash.sh
bash sd_flash.sh /path/to/downloaded/image
```
- Follow the instructions and wait for the SD card to be flashed. 
- Remove the SD card from your PC.
- Ensure your Raspberry Pi 4 is not powered on before inserting the flashed SD card.
- Follow the [Robot Setup](#robot) to configure your TurtleBot 4.