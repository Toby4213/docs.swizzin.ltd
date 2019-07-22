---
id: ombi
title: Ombi
sidebar_label: Ombi
---

Ombi is a self-hosted web application that automatically gives your shared Plex or Emby users the ability to request content by themselves! Ombi can be linked to multiple TV Show and Movie DVR tools to create a seamless end-to-end experience for your users. 

## Initial Setup

Installing Ombi is easy. Simply issue the following command from SSH:

```plaintext main
sudo box install ombi
```

This command will configure and install ombi for your user.

After installation, the files are stored in `/opt/Ombi` and the configuration and database are stored in `/etc/Ombi`

## Upgrading

Ombi is installed and maintained by the unofficially provided repository. In order to keep ombi up-to-date, update your packages with:

```
sudo apt -y update
sudo apt -y upgrade
```

## How to Access

After installation, Ombi will be availabe at the following web address: `https://<hostname.ltd>/ombi`

## Service Management

The systemd service for Ombi is not enabled for use in a multi-user environment.

The service file resides at:

```bash main
/etc/systemd/system/ombi.service
```

<!--DOCUSAURUS_CODE_TABS-->
<!--Start-->
```plaintext
sudo systemctl start ombi
```
<!--Stop-->
```plaintext
sudo systemctl stop ombi
```
<!--Restart-->
```plaintext
sudo systemctl restart ombi
```
<!--Enable-->
```plaintext
sudo systemctl enable ombi
```
<!--Disable-->
```plaintext
sudo systemctl disable ombi
```
<!--END_DOCUSAURUS_CODE_TABS-->

## Configuration

On the first run of Ombi, there will be a brief setup wizard. In order to configure Ombi with Plex, simply choose Plex from the media server options and login to your account with your **plex** username and password. Ombi should now automatically be configured for use with the Plex instance on your server.

If you have further questions about settings and configurations of Ombi, please refer to the [Ombi Wiki](https://github.com/tidusjar/Ombi/wiki).

## Connect to other clients

<!--DOCUSAURUS_CODE_TABS-->
<!--Sonarr-->
::: panel
1. Select Sonarr from the TV Dropdown under settings.
2. In order to configure Sonarr, you must first have a root folder setup. If you haven't set up any root folders in Sonarr, please add a show and setup your Sonarr root show directory first.
3. Use the following configuration:
```plaintext
Enable: checked
Hostname or IP: <subnet IP>
Port: <Sonarr port>
API Key: <API key from dashboard>
Base URL: sonarr
```
4. Click `Load Qualities` and `Load Folders`. Your settings should load successfully.
5. Choose your default quality and folder settings for shows added through Ombi.
6. Submit

:::
<!--Medusa-->
::: panel
1. Select SickRage from the TV Dropdown under settings.
2. Use the following configuration:
```plaintext
Enable: checked
Hostname or IP: <subnet IP>
Port: <your medusa port>
API Key: <your medusa API key>
Base URL: medusa
```
3. Choose a default quality profile.
4. Submit
:::
<!--Radarr-->
::: panel
1. Select Radarr from the Movie Dropdown under settings.
2. In order to configure Radarr, you must first have a root folder setup. If you haven't set up any root folders in Radarr, please add a show and setup your Sonarr root show directory first.
3. Use the following configuration:
```plaintext
Enable: checked
Hostname or IP: <subnet IP>
Port: <Radarr port>
API Key: <API key from dashboard>
Base URL: radarr
```
4. Click `Load Qualities` and `Load Folders`. Your settings should load successfully.
5. Choose your default quality and folder settings for Movies added through Ombi.
6. Submit

:::
<!--END_DOCUSAURUS_CODE_TABS-->

::: tip
In order to connect Ombi to the clients above, you'll need your subnet IP. You can find this on your panel or with the command `cat ~/.install/subnet.lock`
:::