# Jetson_Dli - day03


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

