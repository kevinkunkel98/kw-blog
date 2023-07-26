---
author: Kevin Kunkel
pubDatetime: 2023-07-24T15:20:35Z
title: Post Arch Installation
postSlug: ""
featured: false
draft: false
tags:
  - color-schemes
  - docs
ogImage: ""
description:
  Installing neccesary packages and setting up Arch for daily use.
---

This documentation is a copy paste guide for terminal commands and settings to setup arch linux after a successful installation. I am using KDE Plasma as a desktop environment.
## Table of contents

## Installing useful packages

Install nvidia drivers when using nvidia gpus:

```shell
sudo pacman -S nvidia 
```

Install backends for KDE-Discover to use the software store, `packagekit-qt5` for "normal" packages, `flatpak` for Flatpaks and `fwupd` for firmware updates.

```shell
sudo pacman -S packagekit-qt5 flatpak fwupd
```
Install a fancy terminal theme quickly and easy. First we need the fonts:

```shell
sudo pacman -S powerline-fonts
```
Then we can install the terminal theme which we can config later if we want:

```shell
git clone --recursive https://github.com/andresgongora/synth-shell.git
chmod +x synth-shell/setup.sh
cd synth-shell
./setup.sh
```

## Disable Baloo-Indexer

This process slows down KDE-Plasma by indexing applications. You can simply turn it off

```shell
balooctl stop
balooctl disable
balooctl status
```

For the changes to take affect long-term the system needs to be rebooted:

```shell
reboot
```

## Setting Up Timeshift

Arch tends to not be the most stable system, but we can make it one. One step is to create a Timeshift-Backup-Entry for our grub menu.

> Check out some [predefined color schemes](https://astro-paper.pages.dev/posts/predefined-color-schemes/) AstroPaper has already crafted for you.
