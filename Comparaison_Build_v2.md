# Fedora PS5 Builds — Complete Package Comparison

This document compares the three Fedora-based PlayStation 5 Linux builds by examining their respective `image.yaml` configuration files[cite: 1, 2, 3].

**The objective is to identify:**
- Packages shared by all three builds.
- Packages specific to each build.
- Packages added between the original **PS5-Linux** build and the custom **Desktop Edition**.
- Additional packages introduced by the **Test Build**.
- Differences in system configuration, services, and installation scripts.

---

## 1. Source Repositories

| Build | Repository / Source File | Fedora Version |
| :--- | :--- | :---: |
| **PS5-Linux** | `ps5-linux-image` (`ps5-linux.yaml`)[cite: 3] | Fedora 44[cite: 3] |
| **PS5 Fedora Desktop Edition** | `PS5-Fedora_Desktop-Edition` (`fedora.45-desktop_edition.yaml`)[cite: 1] | Fedora 45[cite: 1] |
| **PS5 Fedora Test Build** | `PS5-Fedora_Test_Build` (`fedora.45-test_build.yaml`)[cite: 2] | Fedora 45[cite: 2] |

**All three builds share the following baseline:**
- **Architecture:** `x86_64`[cite: 1, 2, 3]
- **Package manager:** DNF[cite: 1, 2, 3]
- **Desktop environment:** GNOME[cite: 1, 2, 3]
- **Display protocol:** Wayland[cite: 1, 2, 3]
- **Display manager:** GDM[cite: 1, 2, 3]

---

## 2. Legend

| Symbol | Meaning |
| :---: | :--- |
| ✅ | Explicitly included in the `packages` section of the build |
| ❌ | Not explicitly declared in the `packages` section of the build |

> **Important:** This comparison covers explicitly declared packages in the `packages` lists[cite: 1, 2, 3]. Fedora dependencies and packages/components installed dynamically by build scripts (`actions`) are documented separately in [Section 4](#4-additional-installations-performed-by-build-scripts).

---

## 3. Package Comparison

### 3.1 GNOME Desktop Environment

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `gnome-shell` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-session` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-classic-session` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-terminal` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gdm` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `mutter` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `nautilus` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-control-center` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-settings-daemon` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-keyring` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `seahorse` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `pinentry-gnome3` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `xdg-utils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `xdg-desktop-portal` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `xdg-desktop-portal-gnome` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `xdg-desktop-portal-gtk` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `xdg-user-dirs-gtk` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gvfs` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gvfs-smb` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gvfs-nfs` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gvfs-fuse` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gvfs-mtp` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gvfs-afc` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gvfs-goa` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gvfs-gphoto2` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-backgrounds` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-text-editor` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-system-monitor` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-disk-utility` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-calculator` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-tweaks` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-extensions-app` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-software` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-initial-setup` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-boxes` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-calendar` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-characters` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-clocks` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-color-manager` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-connections` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-contacts` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-epub-thumbnailer` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-font-viewer` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-logs` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-maps` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-remote-desktop` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-user-docs` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-user-share` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-weather` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `file-roller` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `loupe` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `evince` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `papers` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `papers-nautilus` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `baobab` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `sushi` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `showtime` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `decibels` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `snapshot` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `rygel` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `localsearch` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `tinysparql` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `glycin-thumbnailer` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gst-thumbnailers` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `librsvg2` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `vte-profile` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gnome-browser-connector` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `yelp` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `toolbox` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `systemd-oomd-defaults` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `fprintd-pam` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `glib-networking` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `PackageKit-command-not-found` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `PackageKit-gtk3-module` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `xorg-x11-server-Xwayland` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `polkit` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.2 Bluetooth

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `bluez` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `bluez-tools` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gnome-bluetooth` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |

### 3.3 Audio and Multimedia

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `pipewire` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `wireplumber` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `pipewire-pulseaudio` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gstreamer1-plugins-base` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gstreamer1-plugins-good` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gstreamer1-plugins-bad-free` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gstreamer1-plugins-ugly-free` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gstreamer1-libav` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |

### 3.4 Graphics and GPU

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `mesa-dri-drivers` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `mesa-libEGL` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `mesa-vulkan-drivers` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `mesa-va-drivers` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `vulkan-tools` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `mesa-demos` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `libinput` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.5 Networking and File Sharing

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `NetworkManager` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `NetworkManager-wifi` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `network-manager-applet` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `ModemManager` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-adsl` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-libreswan-gnome` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-openconnect-gnome` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-openvpn-gnome` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-ppp` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-ssh-gnome` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `NetworkManager-wwan` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `avahi` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `linux-firmware` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `iw` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `wpa_supplicant` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `wireless-regdb` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `cifs-utils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `samba-client` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `samba` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `nfs-utils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `ethtool` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `nmap-ncat` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `bind-utils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `curl` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `wget` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `pciutils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `usbutils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `util-linux` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.6 Mobile Connectivity

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `gnome-shell-extension-gsconnect` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `fuse-sshfs` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `nautilus-python` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `android-tools` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `wl-clipboard` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |

### 3.7 Printing and Scanning

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `cups` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `cups-filters` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `system-config-printer` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `hplip` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gutenprint-cups` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `splix` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `sane-backends` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `sane-backends-drivers-scanners` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `libsane-hpaio` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `simple-scan` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |

### 3.8 Development Tools

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `git` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `make` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gcc` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gcc-c++` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `gdb` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `cmake` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `ninja-build` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `meson` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `autoconf` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `automake` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `libtool` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `patch` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `binutils` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `pkgconf` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `pkgconf-pkg-config` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `rpm-build` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `python3-pip` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `python3-pyyaml` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `zlib-devel` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `python3-PyQt6` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.9 GTK4 and Libadwaita

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `python3-gobject` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gtk4` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `libadwaita` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `gobject-introspection` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `desktop-file-utils` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `xhost` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.10 Localization and Input

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `glibc-langpack-en` | ✅[cite: 3] | ❌[cite: 1] | ❌[cite: 2] |
| `glibc-all-langpacks` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `langpacks-fr` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `langpacks-en` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `firefox-langpacks` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `xkeyboard-config` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `ibus` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `ibus-gtk3` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `ibus-gtk4` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.11 Base System and Utilities

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `bash-completion` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `zenity` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `newt` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `openssh-server` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `sudo` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `nano` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `dracut` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `kmod` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `e2fsprogs` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `parted` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `cloud-utils-growpart` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `kexec-tools` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `zram-generator-defaults` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `firefox` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `flatpak` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `fuse` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `fuse-libs` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

### 3.12 Fonts

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `dejavu-sans-fonts` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `liberation-fonts` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `adobe-source-code-pro-fonts` | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| `google-noto-sans-fonts` | ✅[cite: 3] | ❌[cite: 1] | ❌[cite: 2] |
| `google-noto-emoji-fonts` | ✅[cite: 3] | ❌[cite: 1] | ❌[cite: 2] |
| `google-noto-color-emoji-fonts` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `google-noto-sans-symbols-fonts` | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| `fontconfig` | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |

---

## 4. Additional Installations Performed by Build Scripts

Some software and configurations are applied through custom shell scripts (`actions`) rather than the `packages` section[cite: 1, 2, 3].

### 4.1 PS5-Linux

- **Packages/files installed via scripts:** Custom PS5 Linux kernel RPM (`/opt/rpms/*.rpm`)[cite: 3], uncompressed AMD PS5 GPU firmware (`cyan_skillfish*`)[cite: 3], and PS5 IW620 WiFi firmware staging (`/usr/local/sbin/ps5-iw620-load`)[cite: 3].
- **Services enabled/configured:** `sshd`, `NetworkManager`, `gdm`, `bluetooth.service`, `grow-rootfs.service`, `ps5-iw620.service`, and `graphical.target`[cite: 3].
- **System configuration:** `root` password locked (`passwd -l root`)[cite: 3], `ps5` user created (`wheel,video,input,render` with passwordless `sudo`)[cite: 3], GDM autologin enabled for `ps5`[cite: 3], `gnome-initial-setup` skipped for `ps5`[cite: 3], ZRAM swap (`zram0`, `ram / 2`, `zstd`)[cite: 3], SELinux disabled[cite: 3], `retries=10` in `/etc/dnf/dnf.conf`[cite: 3].

### 4.2 Desktop Edition — Additional Features

| Component / Addition | Description |
| :--- | :--- |
| **RPM Fusion Free & Nonfree** | Installed via `dnf` in `post-packages` using `rpmfusion-free-release` and `rpmfusion-nonfree-release`[cite: 1] |
| **32-bit Graphics Libraries (`i686`)** | `mesa-vulkan-drivers.i686`, `mesa-dri-drivers.i686`, `libva.i686` installed via `dnf` in `post-packages`[cite: 1] |
| **Flathub & Extension Manager** | Flathub remote added; `com.mattjakeman.ExtensionManager` installed via Flatpak[cite: 1] |
| **Balena Etcher** | Latest `x86_64.rpm` fetched from GitHub releases and installed via `dnf`[cite: 1] |
| **ps5-linux-tools** | Cloned, compiled (`make`), and installed to `/usr/local/sbin/ps5_control`[cite: 1] |
| **Decky Loader** | Installed for user `ps5` via `decky-installer` in `post-files`[cite: 1] |
| **PS5 Fedora Manager** | Cloned from `nexgen999/ps5-fedora-manager` and installed via `./install.sh`[cite: 1] |
| **PS5 Performance Service** | `ps5-performance.service` enabled to run `ps5_control --fan on` and `--boost on`[cite: 1] |
| **PS5 Internal WiFi** | `ps5-iw620.service`, `ps5-iw620-load`, and `ps5-iw620-noautoload.conf` configured and enabled[cite: 1] |
| **Bash Completion** | Global profile script `/etc/profile.d/ps5-bash-completion.sh` enabled for interactive Bash sessions[cite: 1] |

**Additional system configuration:**
- `%_install_langs fr,en` configured in `/etc/rpm/macros.image-language-conf`[cite: 1].
- Automatic GNOME keyring unlocking (`login.keyring` without idle/after lock) configured for `ps5`[cite: 1].
- Custom PS5 kernel RPM installed (`/opt/rpms/*.rpm`), `depmod` run, and `/etc/kernel/postinst.d/zz-update-boot` invoked[cite: 1].
- Uncompressed AMD PS5 GPU firmware (`cyan_skillfish*`), GDM autologin, ZRAM swap, and SELinux disabled[cite: 1].

### 4.3 Test Build — Additional Features

| Component / Addition | Description |
| :--- | :--- |
| **RPM Fusion & Multimedia Codecs** | RPM Fusion Free/Nonfree enabled; `ffmpeg`, `ffmpeg-libs`, `gstreamer1-plugins-bad-freeworld`, and `gstreamer1-plugins-ugly` installed via `dnf` (`--allowerasing --skip-unavailable`)[cite: 2] |
| **32-bit Graphics Libraries (`i686`)** | `mesa-vulkan-drivers.i686`, `mesa-dri-drivers.i686`, `libva.i686` installed via `dnf`[cite: 2] |
| **Flathub & Extension Manager** | Flathub remote added; `com.mattjakeman.ExtensionManager` installed via Flatpak[cite: 2] |
| **Balena Etcher** | Latest `x86_64.rpm` fetched from GitHub releases and installed via `dnf`[cite: 2] |
| **ps5-linux-tools** | Cloned, compiled (`make`), and installed to `/usr/local/sbin/ps5_control`[cite: 2] |
| **Decky Loader** | Installed for user `ps5` via `decky-installer` in `post-files`[cite: 2] |
| **PS5 Fedora Manager** | Cloned from `nexgen999/ps5-fedora-manager` and installed via `./install.sh`[cite: 2] |
| **PS5 Performance Service** | `ps5-performance.service` enabled (`--fan on` and `--boost on`)[cite: 2] |
| **PS5 Internal WiFi** | `ps5-iw620.service`, `ps5-iw620-load`, and `ps5-iw620-noautoload.conf` configured and enabled[cite: 2] |
| **Nautilus & Terminal Helpers** | Adds Nautilus script `"Ouvrir dans le terminal"` and helper `/home/ps5/.local/bin/open-term-here` (using `wl-paste`)[cite: 2] |
| **Bash Completion** | Global profile script `/etc/profile.d/ps5-bash-completion.sh` enabled[cite: 2] |

**Additional system configuration:**
- Services enabled: `sshd`, `NetworkManager`, `avahi-daemon`, `cups`, `gdm`, `bluetooth.service`, `grow-rootfs.service`, `ps5-performance.service`, `ps5-iw620.service`, and `graphical.target`[cite: 2].
- `%_install_langs fr,en` configured in `/etc/rpm/macros.image-language-conf`[cite: 2].
- GDM autologin, automatic GNOME keyring unlocking, ZRAM swap, SELinux disabled, and custom PS5 kernel installation[cite: 2].

---

## 5. Important Differences Between the Builds

| Feature | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| **Fedora 44** | ✅[cite: 3] | ❌[cite: 1] | ❌[cite: 2] |
| **Fedora 45** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **GNOME Desktop** | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **Basic Bluetooth** | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **File sharing (SMB / NFS)** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **Flatpak & Flathub** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **RPM Fusion** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **Development tools** | ❌[cite: 3] | Partial[cite: 1] | Extended[cite: 2] |
| **GTK4 / Libadwaita** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **French localization (`fr`)** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **Mobile connectivity packages** | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| **Printing (`cups`) & Scanning (`sane`)** | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| **Multimedia codecs (`ffmpeg` / GStreamer)** | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |
| **32-bit graphics libraries (`i686`)** | ❌[cite: 3] | Script-installed[cite: 1] | Script-installed[cite: 2] |
| **Decky Loader & PS5 Fedora Manager** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **Automatic PS5 performance service** | ❌[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **PS5 IW620 WiFi service (`ps5-iw620`)** | ✅[cite: 3] | ✅[cite: 1] | ✅[cite: 2] |
| **CUPS & Avahi automatic activation** | ❌[cite: 3] | ❌[cite: 1] | ✅[cite: 2] |

---

## 6. Overall Comparison

### PS5-Linux — Original Build
The original **PS5-Linux** build (Fedora 44) provides a minimal GNOME/Wayland baseline for the PS5[cite: 3]. It includes core desktop, graphics, networking, and system packages, along with PS5 kernel integration, uncompressed AMD GPU firmware, and PS5 IW620 WiFi handling[cite: 3].

### PS5 Fedora Desktop Edition — Desktop Build
The **Desktop Edition** (Fedora 45) builds a lightweight everyday desktop environment (`Lightweight & Essential`)[cite: 1]. It adds SMB/NFS file sharing, GTK4/Libadwaita, Flatpak/Flathub, RPM Fusion, `fr`/`en` localization, 32-bit graphics libraries, Balena Etcher, Decky Loader, PS5 Fedora Manager, and the `ps5-performance` service[cite: 1].

### PS5 Fedora Test Build — Extended Build
The **Test Build** (Fedora 45) expands the desktop configuration (`Full Desktop + Mobile + Print/Scan + Codecs + Dev`)[cite: 2]. It adds extensive GNOME/GTK packages, multimedia packages and codecs (`ffmpeg`, GStreamer), mobile/device tools (`gsconnect`, `android-tools`, `fuse-sshfs`, `wl-clipboard`, `gvfs-*`), printing/scanning (`cups`, `sane`), a broader developer toolchain, Nautilus/terminal helper scripts, and automatic `avahi-daemon` and `cups` services[cite: 2].

---

## 7. Conclusion

| Build | Main Objective |
| :--- | :--- |
| **PS5-Linux** | Minimal Fedora 44 GNOME baseline for PS5[cite: 3] |
| **Desktop Edition** | Lightweight Fedora 45 desktop with PS5 management tools and everyday utilities[cite: 1] |
| **Test Build** | Broad Fedora 45 test environment covering extended desktop, media, mobile, print/scan, and dev tools[cite: 2] |

---

## 8. Comparison Methodology and Limitations

This comparison is based on the provided YAML definitions (`ps5-linux.yaml`, `fedora.45-desktop_edition.yaml`, and `fedora.45-test_build.yaml`)[cite: 1, 2, 3].

- Explicitly listed `packages` may pull in additional dependencies automatically via DNF[cite: 1, 2, 3].
- Shell scripts in `actions` (`post-unpack`, `post-update`, `post-packages`, `post-files`) can install external RPMs/Flatpaks/tools, modify configs, or enable services outside the `packages` list[cite: 1, 2, 3].
- Build scripts and remote repositories referenced in `actions` (such as GitHub releases, RPM Fusion, or Flathub) can evolve over time[cite: 1, 2, 3].

*Last comparison reference: November 2026.*
