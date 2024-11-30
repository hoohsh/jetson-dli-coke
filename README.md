# Jetson nano introduction
# Week 1

## 1. Overview of Jetson Nano Components
![image](https://github.com/user-attachments/assets/9e7ca8ac-d40e-4091-8014-fbe3ecb1fa4d)


### Heatsink
The heatsink is used to cool down the processor of the Jetson Nano. It helps dissipate heat during extended usage, preventing overheating.

### GPIO Pins (General Purpose Input/Output)
These pins allow you to connect various external devices, such as sensors, LEDs, and switches, for control and interaction.

### Micro-USB Port
This port is used to provide power or transfer data. It's commonly used to power the board.

### Ethernet Port
This port is for wired internet connection, allowing the board to connect to a network for data exchange.

### USB 3.0 Ports
High-speed USB ports for fast data transfer. You can connect USB devices like a mouse, keyboard, or external hard drive.

### USB 2.0 Port
A standard USB port for connecting USB devices. It’s slower than USB 3.0 but is widely compatible.

### HDMI Port
Used to connect to a monitor or TV. It supports video and audio output.

### DC Power Jack
A jack for supplying power to the board. Usually, a 5V 4A power adapter is used to ensure stable power.

### Camera Connector
This port is for connecting a MIPI CSI camera module. It’s commonly used in vision projects that utilize Jetson Nano’s AI capabilities.

---

## 2. Ubuntu Installation

Here are the steps to install Ubuntu on the NVIDIA Jetson Nano. Ubuntu is a popular Linux-based operating system, often used for AI, machine learning, and other development projects.

![image](https://github.com/user-attachments/assets/7af3fcef-2ef8-4c98-a1ba-37fccaa8fa47)


### 2.1 Basic System Setup
During the initial setup, you’ll select essential settings, including language, time zone, and keyboard layout to personalize your system.

### 2.2 Installing Essential Software
The installation process will automatically add necessary drivers and software packages required for the Jetson Nano to operate properly.

### 2.3 Network Configuration
You’ll configure the internet connection, allowing for software updates and downloading additional packages that might be needed for development.

### 2.4 Completing the Installation
After the setup, the system will finalize the installation and apply the configurations. Once done, you’ll have a fully functional Ubuntu environment on the Jetson Nano.

---

## 3. Desktop Icons on NVIDIA Jetson Nano with Ubuntu

Here are the main icons displayed on the Ubuntu desktop of the NVIDIA Jetson Nano:
![image](https://github.com/user-attachments/assets/b843fc1d-3502-4a1f-a1ab-5b396efd8fb0)


### 3.1 Chromium Web Browser
A web browser available by default on Ubuntu, used to browse the internet.

### 3.2 NVIDIA Jetson Developer Zone
A link to NVIDIA Jetson's developer resources. Here, you can find materials, guides, and tutorials related to Jetson Nano.

### 3.3 NVIDIA Jetson Zoo
A collection of pre-trained AI models and libraries available for use on the Jetson Nano. These resources are helpful for deep learning and computer vision projects.

### 3.4 NVIDIA Support Forums
A link to the NVIDIA support forums where Jetson users can ask questions, share information, and solve problems together.

### 3.5 L4T README
Documentation related to NVIDIA's L4T (Linux for Tegra) software. This provides instructions on setting up and using L4T on the Jetson Nano.

### 3.6 NVIDIA Jetson Community
A link to the Jetson user community, where users can interact and share knowledge with other Jetson enthusiasts.

---

## 4. Installing Korean Input Method on Ubuntu
![image](https://github.com/user-attachments/assets/252c3afc-3d3f-4660-9f5e-578c08cc52c6)


To install the Korean input method on Ubuntu, follow these steps:

### 4.1 Install Fcitx Korean Input Method
Open the terminal and enter the following commands to install the Fcitx Korean input method:

### 4.2 Change Input Method System
1. Go to **Settings** > **Region & Language**.
2. Click on **Manage Installed Languages** at the bottom.
3. Change the **Input Method System** to **Fcitx**.

### 4.3 Reboot the System
Reboot your system to apply the changes.

### 4.4 Configure Fcitx
1. After rebooting, a **keyboard icon** should appear in the upper right corner of the screen.
2. Click on the icon and select **Configure**.
3. If the icon is not visible, open **Fcitx Configuration** from the applications menu.

### 4.5 Add Korean Input Method
1. In the **Fcitx Configuration** window, go to the **Input Method** tab.
2. Click the **+** button and select **Hangul** to add it.

### 4.6 Set Korean/English Switch Key
1. Go to the **Global Config** tab.
2. Click on **Trigger Input Method**.
3. Press the key you want to use for switching between Korean and English (e.g., the Korean/English key).


# Week 2
### What is jtop?
`jtop` is a powerful tool for monitoring the system status of NVIDIA Jetson devices in real time. Jetson Nano and similar devices provide the following information:
- **Temperature**: Displays the temperature of components such as the CPU, GPU, and PMIC (Power Management IC).
- **Resource Usage**: Monitors CPU and GPU usage, memory and swap usage, and power consumption.
- **Process Management**: Lists running processes and their resource usage.
- **Device Information**: Displays hardware and software details, including the JetPack version.

### Checking Temperature with jtop
To monitor the system temperature, run the following command in the terminal:
jtop


## 2. Installing a Cooling Fan

### Why Install a Cooling Fan?
The Jetson Nano may experience performance degradation or system instability due to high temperatures. Installing a cooling fan helps to manage the device's temperature effectively.


### Installation Steps

1. **Connect the Fan:**
   - Attach the fan's red (+), black (-), and yellow (PWM) wires to the Jetson Nano pin headers.
   - Pin configuration:
     - **5V** (+)
     - **GND** (-)
     - **PWM**

2. **Secure the Fan:**
   - Place the fan on top of the Nano's heatsink and secure it with screws.

3. **Adjust Fan Speed:**
   Run the following command to control the fan's speed:
   sudo sh -c 'echo 128 > /sys/devices/pwm-fan/target_pwm'

Check Temperature: Use the jtop command to verify that the temperature has dropped.
jtop



## 3. Installing and Testing the Camera

### Installing the Camera
1. Plug the USB camera into one of the Jetson Nano's USB ports.
2. Verify the camera connection:
   ls /dev/vi*

Testing the Camera
Navigate to the USB-Camera directory:
cd USB-Camera

List the available scripts in the directory:
ls

Example output:
face-detect-usb.py  LICENSE  README.md  usb-camera-gst.py  usb-camera-simple.py

Run the camera script to test functionality:
python3 usb-camera-gst.py



## 4. Capturing Images

To perform automatic capture, use the following command:
nvgstcapture-1.0 --mode=1 --camsrc=0 --cap-dev-node=0 --automate --capture-auto

Once the camera is active, press J on the keyboard to capture an image:
nvgstcapture-1.0 --mode=1 --camsrc=0 --cap-dev-node=0

![image](https://github.com/user-attachments/assets/912c2915-a036-475b-b730-597fbb7ac841)



## 5. Recording Videos

To record videos, follow these steps:

1. Start video recording:
   nvgstcapture-1.0 --mode=2 --camsrc=0 --cap-dev-node=0

Recording Started(1), Enter (0) to stop OR (2) to take a photo.
Press 0 to stop recording or 2 to capture a snapshot during recording.

we recorded video, recording video url = https://youtu.be/qg-SgLgWycg



# Week 3


<br>


## Preparation

1. Prepare for DLI Docker installation.
2. Install the DLI Docker image.
3. Verify camera functionality.
4. Operate in headless mode:
   - The development environment should not connect the Jetson to a TV.
   - The Jetson should be connected to the internet via Ethernet (wired) or Wi-Fi (wireless).

<br>
<br>


## What is Headless Mode for Jetson Nano?

Headless mode refers to operating the Jetson Nano without a monitor, keyboard, or mouse connected. In this mode:
- The Jetson Nano runs without a graphical user interface (GUI).
- The display remains black, as there is no GUI rendered.

This mode is ideal for remote development and deployment environments, where the Jetson Nano is managed via network access (e.g., SSH) instead of direct physical interaction.


<br>
<br>
<br>

## NVIDIA Jetson Nano DLI AI Development Environment

This script is used to set up a **Deep Learning Development Environment** for **NVIDIA Jetson Nano** using Docker. 

### Purpose:
- Run the **DLI (Digital Learning Institute) AI development environment**.
- Utilize **GPU acceleration** and **camera connectivity** on Jetson Nano.
- Provide a **container-based environment** for sharing datasets or developing deep learning models.

### Script:
```bash
#!/bin/bash

sudo docker run --runtime nvidia -it --rm --network host \
    --memory=500M --memory-swap=4G \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --volume /tmp/argus_socket:/tmp/argus_socket \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.2-r32.7.1kr

dli@dli-desktop:~$ ./docker_dli_run.sh

```

<br>
<br>


## Increase Swap Memory to 18GB After Execution

To increase memory capacity, install an 18GB swap file using the following commands:

```bash
sudo systemctl disable nvzramconfig

sudo systemctl set-default multi-user.target

sudo fallocate -l 18G /mnt/18GB.swap
sudo chmod 600 /mnt/18GB.swap
sudo mkswap /mnt/18GB.swap

sudo su
echo "/mnt/18GB.swap swap swap defaults 0 0" >> /etc/fstab
exit

sudo reboot
```
After rebooting, connect the MICRO 5 PIN.
→ The "L4T connected" notification appears in the bottom-right corner.

<br>

### Set the system to GUI mode.
```
sudo systemctl set-default graphical.target

reboot
```

<br>
<br>

## Thumbs Project

<br>

### Now open a web browser on your computer and enter 'http://192.168.0.204:8888' in the address bar.
password is 'dlinano'

![image](https://github.com/user-attachments/assets/eab669ba-585a-48a2-9096-ae89e084cae1)

Start with classification practice.

<br>

![image](https://github.com/user-attachments/assets/e1ba2991-8bd1-4d2c-84db-9da39fc866e0)

<br>

![image](https://github.com/user-attachments/assets/bc79bdf1-dbe2-4897-98cd-19ffb17b3e63)

<br>

![image](https://github.com/user-attachments/assets/8f51c71e-8bd3-4f64-b216-d2e8b743b789)

<br>

![image](https://github.com/user-attachments/assets/7d068ded-2777-4f9f-8973-6f56df0eb5e0)

<br>

![image](https://github.com/user-attachments/assets/dc4fc18c-6ad2-4366-a05a-c3199f738d7b)

<br>

![image](https://github.com/user-attachments/assets/0333a6e1-372c-4455-9ffe-00c7669cb8ef)

![image](https://github.com/user-attachments/assets/57578bad-0516-4e4f-8a11-3379d6d8560d)

<br>
<br>

## Train the thumb direction.

![image](https://github.com/user-attachments/assets/a2ebdb51-baaa-4b9c-b538-7035a5ddedbb)

<br>

### 1. Data Collection 
1. Choose one of the datasets: A or B.

2. Select the category `thumbs_up`.  
   Point your thumb upward and click the `add` button about 30 times to capture images.

3. Then, select the category `thumbs_down`.  
   Point your thumb downward and click the `add` button about 30 times to capture images.

![image](https://github.com/user-attachments/assets/b99fdbfd-f79f-4a68-904a-40ec85bebef3)

### 2. Training
After capturing all the images, click the `train` button to start the training process.  
You can monitor the progress using the progress bar.

### 3. Test
Click the 'live' button in the top-right corner of the state to start testing.

<br>

- When you raise your thumb upward, you can see the 'thumbs_up' ratio increase.

![image](https://github.com/user-attachments/assets/5d735914-8c3c-4b53-95cc-67175dfb214a)

<br>

- When you point your thumb downward, you can see the 'thumbs_down' ratio increase.

![image](https://github.com/user-attachments/assets/ef28288f-86b3-4e88-9a0c-5fc056363a5f)

