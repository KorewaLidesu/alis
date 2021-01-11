# alis (by picodotdev)
~~A fork for my installation. Please use the original instead.~~

Arch Linux Install Script (or alis) installs unattended, automated and customized Arch Linux system.

It is a simple bash script that fully automates the installation of a Arch Linux system after booting from the original Arch Linux installation media. It contains the same commands that you would type and execute one by one interactively to complete the installation. The only user intervention needed is to edit a configuration file to choose the installation options and preferences from partitioning, to encryption, bootloader, file system, language and keyboard mapping, desktop environment, kernels, packages to install and graphic drivers. This automation makes the installation easy and fast.

If some time later after an system update for any reason the system does not boot correctly a recovery script is also provided to enter in a recovery mode that allows to downgrade packages or execute any other commands to restore the system. Also a log of the installation can be taken with <a href="https://asciinema.org/">asciinema</a>.

Currently these scripts are for me but maybe they are useful for you too.

### Donations (to picodotdev)

If you find useful the ~~original~~ script, you can support picodotdev with a [small donation](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=3PF47D5TSNL7C&currency_code=EUR) through PayPal to continue adding features, updating the script, accepting pull request and responding to any question. Also there are other ways you can contribute in the [How you can help](https://github.com/picodotdev/alis#how-you-can-help) section.

[![Donate with PayPal button](https://www.paypalobjects.com/en_US/ES/i/btn/btn_donateCC_LG.gif "PayPal - The safer, easier way to pay online!")](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=3PF47D5TSNL7C&currency_code=EUR)

### Features

* **System**: BIOS
* **Storage**: SATA
* **Encryption**: root partition encrypted and no encrypted
* **Partition**: MBR on BIOS
* **File system**: ext4
* **Kernels**: linux
* **Desktop environment**: none
* **Display managers**: none
* **Graphics controller**: amd. With intel optionally fastboot, hardware video acceleration and framebuffer compression.
* **Bootloader**: GRUB
* **Custom shell**: bash
* **WPA WIFI network** installation: NO!!!
* **Periodic TRIM** for SSD storage: NO!!!
* Intel and AMD **processors microcode**
* Optional **swap file**
* **VirtualBox guest additions** : NO!!!
* **Kernel compression** and **custom parameters**
* **Users creation** and **add to sudoers**
* **systemd units enable or disable**
* **Multilib** support
* **Arch Linux** common and custom **packages installation**
* Flatpak utility installation and **Flatpak packages installation**
* SDKMAN utility installation and **SDKMAN packages installation**
* **AUR utility** installation (yay, aurman) and **AUR packages installation**
* **Packages installation after base system installation** (preferred way of packages installation)
* Script for download installation and **recovery scripts** and configuration files
* **Retry packages download** on connection/mirror error
* **Packer support** for testing in VirtualBox
* **Installation log** with all commands executed and output in a file and/or **asciinema video**
* Wait after installation for an **abortable reboot**
* Fork the repository and **use your own configuration**: Yes.

### System installation

Download and boot from the latest <a href="https://www.archlinux.org/download/">original Arch Linux installation media</a>. After boot use the following commands to start the installation.

Follow the <a href="https://wiki.archlinux.org/index.php/Arch_Linux">Arch Way</a> of doing things and learn what this script does. This will allow you to know what is happening. 

Internet connection is required, with wireless WIFI connection see <a href="https://wiki.archlinux.org/index.php/Wireless_network_configuration#Wi-Fi_Protected_Access">Wireless_network_configuration</a> to bring up WIFI connection before start the installation.

```
#                         # Start the system with latest Arch Linux installation media
# loadkeys [keymap]       # Load keyboard keymap, eg. loadkeys es, loadkeys us, loadkeys de
# curl -sL https://raw.githubusercontent.com/picodotdev/alis/master/download.sh | bash     # Download alis scripts
# # curl -sL https://bit.ly/2F3CATp | bash                                                 # Alternative download URL with URL shortener
# ./alis-asciinema.sh     # (Optional) Start asciinema video recording
# vim alis.conf           # Edit configuration and change variables values with your preferences (system configuration)
# vim alis-packages.conf  # (Optional) Edit configuration and change variables values with your preferences (packages to install)
#                         # (The preferred way to install packages is after system installation, see Packages installation)
# ./alis.sh               # Start installation
# ./alis-reboot.sh        # (Optional) Reboot the system, only necessary when REBOOT="false"
```

### Packages installation

After the base Arch Linux system is installed, alis can install packages with pacman, Flatpak, SDKMAN and from AUR.

```
#                                  # After system installation start a user session
# curl -sL https://raw.githubusercontent.com/picodotdev/alis/master/download.sh | bash     # Download alis scripts
# # curl -sL https://bit.ly/2F3CATp | bash                                                 # Alternative download URL with URL shortener
# ./alis-packages-asciinema.sh     # (Optional) Start asciinema video recording
# vim alis-packages.conf           # Edit configuration and change variables values with your preferences (packages to install)
# ./alis-packages.sh               # Start packages installation
```

### Recovery

Boot from the latest <a href="https://www.archlinux.org/download/">original Arch Linux installation media</a>. After boot use the following commands to start the recovery, this will allow you to enter in the arch-chroot environment.

```
#                                  # Start the system with latest Arch Linux installation media
# loadkeys [keymap]                # Load keyboard keymap, eg. loadkeys es, loadkeys us, loadkeys de
# curl -sL https://raw.githubusercontent.com/picodotdev/alis/master/download.sh | bash     # Download alis scripts
# # curl -sL http://tiny.cc/alisLi | bash                                                  # Alternative download URL with URL shortener
# ./alis-recovery-asciinema.sh     # (Optional) Start asciinema video recording
# vim alis-recovery.conf           # Edit configuration and change variables values with your last installation configuration with alis (mainly device and partition scheme)
# ./alis-recovery.sh               # Start recovery
# ./alis-recovery-reboot.sh        # Reboot the system
```

### Arch Linux Installation Media

https://www.archlinux.org/download/
