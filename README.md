# Jetson nano introduction
# Day 1

## 1. Overview of Jetson Nano Components

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
