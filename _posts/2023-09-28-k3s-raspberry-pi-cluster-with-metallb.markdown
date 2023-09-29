---
layout: post
title: K3S Raspberry Pi cluster with MetalLB
subtitle: build a k3s cluster
description: Setup a homelab kubernetes cluster using raspberry pi's, k3s and MetalLB
categories: [Kubernetes]
tags: [k3s, k8s, raspberry-pi, metallb]
---


## Introduction

In this blog post, I will share my experience of setting up a small k3s (kubernetes) cluster using Raspberry Pis. From the initial hardware setup to the software configurations, you'll learn how I got the cluster up and running. Let's start with a brief outline of the hardware setup before diving into the software side of things.

### My Hardware Setup

![Parts to build a raspberry pi kubernetes cluster][1]

- 3 x [Raspberry Pi 4](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)
- 3 x [Samsung MicroSDXC Memory Card](https://www.amazon.co.uk/Samsung-microSDXC-SD-Adapter-MB-ME64KA-EU/dp/B09D3N56DD)
- 1 x [Netgear PoE Switch 8 Port](https://www.amazon.co.uk/NETGEAR-Gigabit-Ethernet-Managed-GS308EPP/dp/B08PBXMHRR)
- 3 x Short Cat 6 Ethernet cables
- 3 x [Raspberry Pi 4 PoE Hat](https://www.raspberrypi.com/products/poe-hat/)
- 1 x Consumer Router e.g. [FRITZ!Box](https://en.avm.de/products/fritzbox/)

## Installing Ubuntu on Raspberry Pis

First, let's go over the process of installing Ubuntu on our Raspberry Pis using the Raspberry Pi Imager tool.

1. Download and install the Raspberry Pi Imager tool from https://www.raspberrypi.org/software/.
1. Open the Raspberry Pi Imager and select "Choose OS."
1. Scroll down and select "Ubuntu" from the list of Operating Systems.
1. Choose the version of Ubuntu you'd like to install (In this case, it's recommended to choose Ubuntu 20.04 LTS for Raspberry Pi 4/400).
1. Insert your Samsung SD card into your computer.
1. Select "Choose SD Card" and choose the SD card you just inserted.
1. Click on "Write" to start the process.

The Imager tool will now write the Ubuntu image to the SD card, and once it's finished, you can insert the SD cards into your Raspberry Pis.

## Set Hostnames on Ubuntu

Once you have Ubuntu up and running on your Raspberry Pis, you need to set the hostnames to make it easier to identify and manage the nodes in your cluster. I've gone with an Avengers theme; capt (master node), thor and hulk (worker nodes). 

1. Log in to each Raspberry Pi via SSH.

1. Using the hostnamectl command give the Pi a new name

    ```bash
    sudo hostnamectl set-hostname new-name
    ```

1. Next edit the /etc/hosts file, you could use nano or vi to do this and replace any existing occurance of the existing pi name with your new hostname

    ```bash
    sudo nano /etc/hosts
    ```

1. Save the changes and reboot the pi 

    ```bash
    sudo reboot
    ```


[1]: /assets/img/raspberry-pi-cluster-parts.jpeg