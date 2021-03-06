---
id: emby
title: Emby
sidebar_label: Emby
---

Take your home videos, music, and photos with you wherever you go, even offline with Emby Mobile Sync. Emby mobile apps are available for Android, iPhone, iPad, Windows Phone and Windows Tablets.

Or sit back and enjoy Emby from the living room. Emby apps are available for Android TV, Amazon Fire TV, Chromecast, Roku, Xbox, Home Theater Computers, and more.


## Initial Setup

Installing emby is easy. Simply issue the following command from SSH:

```bash main
sudo box install emby
```

This command will configure an emby docker container for your user.

## How to Access

Emby can be accessed from your browser at `https://<hostname.ltd>/emby/`

## Service Management

The systemd service file for Emby is the default file. No modifications have been made to change its arguments.

<!--DOCUSAURUS_CODE_TABS-->
<!--Start-->
```bash
sudo systemctl start emby-server
```
<!--Stop-->
```bash
sudo systemctl stop emby-server
```
<!--Restart-->
```bash
sudo systemctl restart emby-server
```
<!--Enable-->
```bash
sudo systemctl enable emby-server
```
<!--Disable-->
```bash
sudo systemctl disable emby-server
```
<!--END_DOCUSAURUS_CODE_TABS-->

## Configuration

When you load up Emby for the first time, you'll be greeted by the setup wizard. Setup is fairly straightforward.


## Further setup

While not covered in this documentation, there are further guides and documentations on the [Emby Forum](https://emby.media/community/index.php?/forum/24-tutorials-and-guides/)