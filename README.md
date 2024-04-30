# Debian 12 on Raspberry Pi 4 with AdGuard Home and Unbound (DoT)

### Setting up Debian 12 on Raspberry Pi 4 via SSH

This guide provides detailed instructions on how to install Debian 12 on a Raspberry Pi 4 using only SSH access from a Windows machine. The procedure includes downloading and flashing the Debian image, configuring SSH access, and initial boot settings. This setup is ideal for scenarios where direct access to the Raspberry Pi is limited.

### Prerequisites

- Raspberry Pi 4 with an Ethernet connection
- MicroSD card (16GB or larger recommended)
- A Windows computer with internet access
- SSH client installed on the Windows computer

#### Installation Steps

#### 1. Prepare the Installation Image

- Download and install the **Raspberry Pi Imager** from the official Raspberry Pi website:

[https://www.raspberrypi.com/software/](https://www.raspberrypi.com/software/)



- Obtain the stable Debian image for Raspberry Pi. You can choose from daily or tested images. For this guide, the daily images are used:

[https://raspi.debian.net/daily-images/](https://raspi.debian.net/daily-images/)


#### 2. Flash the Debian Image

- Open Raspberry Pi Imager.
- Select the downloaded Debian image and flash it to the MicroSD card. Avoid altering any custom settings provided by the Raspberry Pi Imager.

#### 3. Configure SSH Access

- After the image is flashed, navigate to the `raspifirm` directory on the MicroSD card.
- Open the `sysconf` file for editing.
- Generate an SSH key pair by running the following command in a Windows Command Prompt:
```
ssh-keygen -t rsa
```
- Save the key to the default location as prompted.
- Uncomment and edit the `ssh passkey=` line in the `sysconf` file. Paste the contents of your `id_rsa.pub` file here.

#### 4. Set Hostname (Optional)

- If you wish to set a custom hostname for your Raspberry Pi, uncomment the `hostname` variable in the `sysconf` file and specify your desired hostname.

#### 5. Finalize and Boot

- Save the changes to the `sysconf` file.
- Safely eject the MicroSD card from your computer and insert it into your Raspberry Pi.
- Connect your Raspberry Pi to a power source and Ethernet.
- Boot up the Raspberry Pi. It should be accessible via SSH from your Windows machine using the IP address assigned to it on your network.

### Connecting to Your Raspberry Pi

- To connect to your Raspberry Pi via SSH, use the following command in your SSH client:
```
ssh root@<IP_ADDRESS>
```
Replace `<IP_ADDRESS>` with the actual IP address of your Raspberry Pi.

Type `yes` when prompted

**This portion should help you set up a Raspberry Pi with Debian 12 for remote management and configuration over SSH. For further customization and configuration, refer to the Debian and Raspberry Pi documentation.
**
