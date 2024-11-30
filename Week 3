# Jetson_Dli - day03
---

## Preparation

1. Prepare for DLI Docker installation.
2. Install the DLI Docker image.
3. Verify camera functionality.
4. Operate in headless mode:
   - The development environment should not connect the Jetson to a TV.
   - The Jetson should be connected to the internet via Ethernet (wired) or Wi-Fi (wireless).

---

## What is Headless Mode for Jetson Nano?

Headless mode refers to operating the Jetson Nano without a monitor, keyboard, or mouse connected. In this mode:
- The Jetson Nano runs without a graphical user interface (GUI).
- The display remains black, as there is no GUI rendered.

This mode is ideal for remote development and deployment environments, where the Jetson Nano is managed via network access (e.g., SSH) instead of direct physical interaction.

---

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
