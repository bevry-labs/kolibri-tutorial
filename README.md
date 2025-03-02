# Kolibri Tutorial

I will be setting up [Kolibri](https://learningequality.org/kolibri/about-kolibri/) for two Indonesian schools in the remote island of Sumba.

Hardware will be a Raspberry Pi 5 8GB with 256GB Sandisk Endurance SD Card per school.

## Raspberry Pi OS Lite / Debian

This installation technique was mentioned:

- https://kolibri.readthedocs.io/en/latest/install/raspberry_pi.html#debian-package
- https://kolibri.readthedocs.io/en/latest/install/ubuntu-debian.html#kolibri-server-package

However, it failed on:

```
$ sudo add-apt-repository ppa:learningequality/kolibri
sudo: add-apt-repository: command not found
```

![01-add-apt-repository-not-found.png](https://github.com/bevry-labs/kolibri-tutorial/blob/main/01-add-apt-repository-not-found.png?raw=true)

## Raspberry Pi Image

The Raspberry Pi Image is the next installation technique that I tried:

- https://kolibri.readthedocs.io/en/latest/install/raspberry_pi.html#raspberry-pi

The documentation mentions:

> Kolibri is tested to work on Raspberry Pi Models 3, 3+, 4 and Zero W.
> Download the Raspberry Pi ZIP file for Kolibri version 0.16, or have it copied to your local drive.

However, the download link goes to `kolibri-pi-image-0.17.5.zip` which is fortunate, as the forums indicate:

> The latest Kolibri image for Raspberry Pi should be compatible now. As of now, that Kolibri version is 0.17.5 and you can find the image on our download page: Download Kolibri - Learning Equality
> https://community.learningequality.org/t/raspberry-pi-5-img/3142/6?u=balupton

Downloading via Safari was still waiting to start after several minutes, so  I used [Dorothy](https://github.com/bevry/dorothy)'s `down` command instead, which took a minute:

```
down 'https://storage.googleapis.com/le-releases/downloads/kolibri/v0.17.5/kolibri-pi-image-0.17.5.zip'
```

I used Rasberry Pi Imager with `Use Custom` to select the `.zip` file directly.

I used a custom hostname, username and password, and included my public SSH key, however it did not seem to use any of that:

![03-custom-user-and-hostname-and-ssh-public-key-not-applied.png](https://github.com/bevry-labs/kolibri-tutorial/blob/main/03-custom-user-and-hostname-and-ssh-public-key-not-applied.png?raw=true)

![04-still-default-config.png](https://github.com/bevry-labs/kolibri-tutorial/blob/main/04-still-default-config.png?raw=true)

### Second Attempt, No Customisations

