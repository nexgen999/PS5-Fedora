# Fedora PS5 Builds — Complete Package Comparison

This document compares the three Fedora-based PlayStation 5 Linux builds by examining their respective `image.yaml` configuration files.

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
| **PS5-Linux** | `ps5-linux-image` (`ps5-linux.yaml`) | Fedora 44 |
| **PS5 Fedora Desktop Edition** | `PS5-Fedora_Desktop-Edition` (`fedora.45-desktop_edition.yaml`) | Fedora 45 |
| **PS5 Fedora Test Build** | `PS5-Fedora_Test_Build` (`fedora.45-test_build.yaml`) | Fedora 45 |

**All three builds share the following baseline:**
- **Architecture:** `x86_64`
- **Package manager:** DNF
- **Desktop environment:** GNOME
- **Display protocol:** Wayland
- **Display manager:** GDM

---

## 2. Legend

| Symbol | Meaning |
| :---: | :--- |
| ✅ | Explicitly included in the `packages` section of the build |
| ❌ | Not explicitly declared in the `packages` section of the build |

> **Important:** This comparison covers explicitly declared packages in the `packages` lists. Fedora dependencies and packages/components installed dynamically by build scripts (`actions`) are documented separately in [Section 4](#4-additional-installations-performed-by-build-scripts).

---

## 3. Package Comparison

### 3.1 GNOME Desktop Environment

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `gnome-shell` | ✅ | ✅ | ✅ |
| `gnome-session` | ✅ | ✅ | ✅ |
| `gnome-classic-session` | ❌ | ❌ | ✅ |
| `gnome-terminal` | ✅ | ✅ | ✅ |
| `gdm` | ✅ | ✅ | ✅ |
| `mutter` | ✅ | ✅ | ✅ |
| `nautilus` | ✅ | ✅ | ✅ |
| `gnome-control-center` | ✅ | ✅ | ✅ |
| `gnome-settings-daemon` | ✅ | ✅ | ✅ |
| `gnome-keyring` | ✅ | ✅ | ✅ |
| `seahorse` | ❌ | ✅ | ✅ |
| `pinentry-gnome3` | ❌ | ✅ | ✅ |
| `xdg-utils` | ❌ | ✅ | ✅ |
| `xdg-desktop-portal` | ❌ | ❌ | ✅ |
| `xdg-desktop-portal-gnome` | ✅ | ✅ | ✅ |
| `xdg-desktop-portal-gtk` | ❌ | ❌ | ✅ |
| `xdg-user-dirs-gtk` | ✅ | ✅ | ✅ |
| `gvfs` | ❌ | ✅ | ✅ |
| `gvfs-smb` | ❌ | ✅ | ✅ |
| `gvfs-nfs` | ❌ | ✅ | ✅ |
| `gvfs-fuse` | ❌ | ✅ | ✅ |
| `gvfs-mtp` | ❌ | ❌ | ✅ |
| `gvfs-afc` | ❌ | ❌ | ✅ |
| `gvfs-goa` | ❌ | ❌ | ✅ |
| `gvfs-gphoto2` | ❌ | ❌ | ✅ |
| `gnome-backgrounds` | ✅ | ✅ | ✅ |
| `gnome-text-editor` | ✅ | ✅ | ✅ |
| `gnome-system-monitor` | ✅ | ✅ | ✅ |
| `gnome-disk-utility` | ✅ | ✅ | ✅ |
| `gnome-calculator` | ✅ | ✅ | ✅ |
| `gnome-tweaks` | ✅ | ✅ | ✅ |
| `gnome-extensions-app` | ✅ | ✅ | ✅ |
| `gnome-software` | ✅ | ✅ | ✅ |
| `gnome-initial-setup` | ✅ | ✅ | ✅ |
| `gnome-boxes` | ❌ | ❌ | ✅ |
| `gnome-calendar` | ❌ | ❌ | ✅ |
| `gnome-characters` | ❌ | ❌ | ✅ |
| `gnome-clocks` | ❌ | ❌ | ✅ |
| `gnome-color-manager` | ❌ | ❌ | ✅ |
| `gnome-connections` | ❌ | ❌ | ✅ |
| `gnome-contacts` | ❌ | ❌ | ✅ |
| `gnome-epub-thumbnailer` | ❌ | ❌ | ✅ |
| `gnome-font-viewer` | ❌ | ❌ | ✅ |
| `gnome-logs` | ❌ | ❌ | ✅ |
| `gnome-maps` | ❌ | ❌ | ✅ |
| `gnome-remote-desktop` | ❌ | ❌ | ✅ |
| `gnome-user-docs` | ❌ | ❌ | ✅ |
| `gnome-user-share` | ❌ | ❌ | ✅ |
| `gnome-weather` | ❌ | ❌ | ✅ |
| `file-roller` | ✅ | ✅ | ✅ |
| `loupe` | ✅ | ✅ | ✅ |
| `evince` | ✅ | ✅ | ✅ |
| `papers` | ❌ | ❌ | ✅ |
| `papers-nautilus` | ❌ | ❌ | ✅ |
| `baobab` | ✅ | ✅ | ✅ |
| `sushi` | ❌ | ❌ | ✅ |
| `showtime` | ❌ | ❌ | ✅ |
| `decibels` | ❌ | ❌ | ✅ |
| `snapshot` | ❌ | ❌ | ✅ |
| `rygel` | ❌ | ❌ | ✅ |
| `localsearch` | ❌ | ❌ | ✅ |
| `tinysparql` | ❌ | ❌ | ✅ |
| `glycin-thumbnailer` | ❌ | ❌ | ✅ |
| `gst-thumbnailers` | ❌ | ❌ | ✅ |
| `librsvg2` | ❌ | ❌ | ✅ |
| `vte-profile` | ❌ | ❌ | ✅ |
| `gnome-browser-connector` | ❌ | ❌ | ✅ |
| `yelp` | ❌ | ❌ | ✅ |
| `toolbox` | ❌ | ❌ | ✅ |
| `systemd-oomd-defaults` | ❌ | ❌ | ✅ |
| `fprintd-pam` | ❌ | ❌ | ✅ |
| `glib-networking` | ❌ | ❌ | ✅ |
| `PackageKit-command-not-found` | ❌ | ❌ | ✅ |
| `PackageKit-gtk3-module` | ❌ | ❌ | ✅ |
| `xorg-x11-server-Xwayland` | ✅ | ✅ | ✅ |
| `polkit` | ✅ | ✅ | ✅ |

### 3.2 Bluetooth

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `bluez` | ✅ | ✅ | ✅ |
| `bluez-tools` | ✅ | ✅ | ✅ |
| `gnome-bluetooth` | ❌ | ❌ | ✅ |

### 3.3 Audio and Multimedia

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `pipewire` | ✅ | ✅ | ✅ |
| `wireplumber` | ✅ | ✅ | ✅ |
| `pipewire-pulseaudio` | ✅ | ✅ | ✅ |
| `gstreamer1-plugins-base` | ❌ | ❌ | ✅ |
| `gstreamer1-plugins-good` | ❌ | ❌ | ✅ |
| `gstreamer1-plugins-bad-free` | ❌ | ❌ | ✅ |
| `gstreamer1-plugins-ugly-free` | ❌ | ❌ | ✅ |
| `gstreamer1-libav` | ❌ | ❌ | ✅ |

### 3.4 Graphics and GPU

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `mesa-dri-drivers` | ✅ | ✅ | ✅ |
| `mesa-libEGL` | ❌ | ❌ | ✅ |
| `mesa-vulkan-drivers` | ✅ | ✅ | ✅ |
| `mesa-va-drivers` | ✅ | ✅ | ✅ |
| `vulkan-tools` | ❌ | ✅ | ✅ |
| `mesa-demos` | ❌ | ✅ | ✅ |
| `libinput` | ✅ | ✅ | ✅ |

### 3.5 Networking and File Sharing

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `NetworkManager` | ✅ | ✅ | ✅ |
| `NetworkManager-wifi` | ✅ | ✅ | ✅ |
| `network-manager-applet` | ✅ | ✅ | ✅ |
| `ModemManager` | ❌ | ❌ | ✅ |
| `NetworkManager-adsl` | ❌ | ❌ | ✅ |
| `NetworkManager-libreswan-gnome` | ❌ | ❌ | ✅ |
| `NetworkManager-openconnect-gnome` | ❌ | ❌ | ✅ |
| `NetworkManager-openvpn-gnome` | ❌ | ❌ | ✅ |
| `NetworkManager-ppp` | ❌ | ❌ | ✅ |
| `NetworkManager-ssh-gnome` | ❌ | ❌ | ✅ |
| `NetworkManager-wwan` | ❌ | ❌ | ✅ |
| `avahi` | ❌ | ❌ | ✅ |
| `linux-firmware` | ✅ | ✅ | ✅ |
| `iw` | ✅ | ✅ | ✅ |
| `wpa_supplicant` | ✅ | ✅ | ✅ |
| `wireless-regdb` | ✅ | ✅ | ✅ |
| `cifs-utils` | ❌ | ✅ | ✅ |
| `samba-client` | ❌ | ✅ | ✅ |
| `samba` | ❌ | ✅ | ✅ |
| `nfs-utils` | ❌ | ✅ | ✅ |
| `ethtool` | ❌ | ✅ | ✅ |
| `nmap-ncat` | ❌ | ✅ | ✅ |
| `bind-utils` | ❌ | ✅ | ✅ |
| `curl` | ❌ | ✅ | ✅ |
| `wget` | ❌ | ✅ | ✅ |
| `pciutils` | ❌ | ✅ | ✅ |
| `usbutils` | ❌ | ✅ | ✅ |
| `util-linux` | ✅ | ✅ | ✅ |

### 3.6 Mobile Connectivity

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `gnome-shell-extension-gsconnect` | ❌ | ❌ | ✅ |
| `fuse-sshfs` | ❌ | ❌ | ✅ |
| `nautilus-python` | ❌ | ❌ | ✅ |
| `android-tools` | ❌ | ❌ | ✅ |
| `wl-clipboard` | ❌ | ❌ | ✅ |

### 3.7 Printing and Scanning

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `cups` | ❌ | ❌ | ✅ |
| `cups-filters` | ❌ | ❌ | ✅ |
| `system-config-printer` | ❌ | ❌ | ✅ |
| `hplip` | ❌ | ❌ | ✅ |
| `gutenprint-cups` | ❌ | ❌ | ✅ |
| `splix` | ❌ | ❌ | ✅ |
| `sane-backends` | ❌ | ❌ | ✅ |
| `sane-backends-drivers-scanners` | ❌ | ❌ | ✅ |
| `libsane-hpaio` | ❌ | ❌ | ✅ |
| `simple-scan` | ❌ | ❌ | ✅ |

### 3.8 Development Tools

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `git` | ❌ | ✅ | ✅ |
| `make` | ❌ | ✅ | ✅ |
| `gcc` | ❌ | ✅ | ✅ |
| `gcc-c++` | ❌ | ❌ | ✅ |
| `gdb` | ❌ | ❌ | ✅ |
| `cmake` | ❌ | ❌ | ✅ |
| `ninja-build` | ❌ | ❌ | ✅ |
| `meson` | ❌ | ❌ | ✅ |
| `autoconf` | ❌ | ❌ | ✅ |
| `automake` | ❌ | ❌ | ✅ |
| `libtool` | ❌ | ❌ | ✅ |
| `patch` | ❌ | ❌ | ✅ |
| `binutils` | ❌ | ❌ | ✅ |
| `pkgconf` | ❌ | ❌ | ✅ |
| `pkgconf-pkg-config` | ❌ | ❌ | ✅ |
| `rpm-build` | ❌ | ❌ | ✅ |
| `python3-pip` | ❌ | ❌ | ✅ |
| `python3-pyyaml` | ❌ | ❌ | ✅ |
| `zlib-devel` | ❌ | ✅ | ✅ |
| `python3-PyQt6` | ❌ | ✅ | ✅ |

### 3.9 GTK4 and Libadwaita

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `python3-gobject` | ❌ | ✅ | ✅ |
| `gtk4` | ❌ | ✅ | ✅ |
| `libadwaita` | ❌ | ✅ | ✅ |
| `gobject-introspection` | ❌ | ✅ | ✅ |
| `desktop-file-utils` | ❌ | ✅ | ✅ |
| `xhost` | ❌ | ✅ | ✅ |

### 3.10 Localization and Input

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `glibc-langpack-en` | ✅ | ❌ | ❌ |
| `glibc-all-langpacks` | ❌ | ✅ | ✅ |
| `langpacks-fr` | ❌ | ✅ | ✅ |
| `langpacks-en` | ❌ | ✅ | ✅ |
| `firefox-langpacks` | ❌ | ✅ | ✅ |
| `xkeyboard-config` | ❌ | ✅ | ✅ |
| `ibus` | ❌ | ✅ | ✅ |
| `ibus-gtk3` | ❌ | ✅ | ✅ |
| `ibus-gtk4` | ❌ | ✅ | ✅ |

### 3.11 Base System and Utilities

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `bash-completion` | ❌ | ✅ | ✅ |
| `zenity` | ❌ | ✅ | ✅ |
| `newt` | ❌ | ✅ | ✅ |
| `openssh-server` | ✅ | ✅ | ✅ |
| `sudo` | ✅ | ✅ | ✅ |
| `nano` | ✅ | ✅ | ✅ |
| `dracut` | ✅ | ✅ | ✅ |
| `kmod` | ✅ | ✅ | ✅ |
| `e2fsprogs` | ✅ | ✅ | ✅ |
| `parted` | ✅ | ✅ | ✅ |
| `cloud-utils-growpart` | ✅ | ✅ | ✅ |
| `kexec-tools` | ✅ | ✅ | ✅ |
| `zram-generator-defaults` | ✅ | ✅ | ✅ |
| `firefox` | ✅ | ✅ | ✅ |
| `flatpak` | ❌ | ✅ | ✅ |
| `fuse` | ❌ | ✅ | ✅ |
| `fuse-libs` | ❌ | ✅ | ✅ |

### 3.12 Fonts

| Package | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `dejavu-sans-fonts` | ✅ | ✅ | ✅ |
| `liberation-fonts` | ✅ | ✅ | ✅ |
| `adobe-source-code-pro-fonts` | ❌ | ❌ | ✅ |
| `google-noto-sans-fonts` | ✅ | ❌ | ❌ |
| `google-noto-emoji-fonts` | ✅ | ❌ | ❌ |
| `google-noto-color-emoji-fonts` | ❌ | ✅ | ✅ |
| `google-noto-sans-symbols-fonts` | ❌ | ✅ | ✅ |
| `fontconfig` | ✅ | ✅ | ✅ |

---

## 4. Additional Installations Performed by Build Scripts

Some software and configurations are applied through custom shell scripts (`actions`) rather than the `packages` section.

### 4.1 PS5-Linux

- **Packages/files installed via scripts:** Custom PS5 Linux kernel RPM (`/opt/rpms/*.rpm`), uncompressed AMD PS5 GPU firmware (`cyan_skillfish*`), and PS5 IW620 WiFi firmware staging (`/usr/local/sbin/ps5-iw620-load`).
- **Services enabled/configured:** `sshd`, `NetworkManager`, `gdm`, `bluetooth.service`, `grow-rootfs.service`, `ps5-iw620.service`, and `graphical.target`.
- **System configuration:** `root` password locked (`passwd -l root`), `ps5` user created (`wheel,video,input,render` with passwordless `sudo`), GDM autologin enabled for `ps5`, `gnome-initial-setup` skipped for `ps5`, ZRAM swap (`zram0`, `ram / 2`, `zstd`), SELinux disabled, `retries=10` in `/etc/dnf/dnf.conf`.

### 4.2 Desktop Edition — Additional Features

| Component / Addition | Description |
| :--- | :--- |
| **RPM Fusion Free & Nonfree** | Installed via `dnf` in `post-packages` using `rpmfusion-free-release` and `rpmfusion-nonfree-release` |
| **32-bit Graphics Libraries (`i686`)** | `mesa-vulkan-drivers.i686`, `mesa-dri-drivers.i686`, `libva.i686` installed via `dnf` in `post-packages` |
| **Flathub & Extension Manager** | Flathub remote added; `com.mattjakeman.ExtensionManager` installed via Flatpak |
| **Balena Etcher** | Latest `x86_64.rpm` fetched from GitHub releases and installed via `dnf` |
| **ps5-linux-tools** | Cloned, compiled (`make`), and installed to `/usr/local/sbin/ps5_control` |
| **Decky Loader** | Installed for user `ps5` via `decky-installer` in `post-files` |
| **PS5 Fedora Manager** | Cloned from `nexgen999/ps5-fedora-manager` and installed via `./install.sh` |
| **PS5 Performance Service** | `ps5-performance.service` enabled to run `ps5_control --fan on` and `--boost on` |
| **PS5 Internal WiFi** | `ps5-iw620.service`, `ps5-iw620-load`, and `ps5-iw620-noautoload.conf` configured and enabled |
| **Bash Completion** | Global profile script `/etc/profile.d/ps5-bash-completion.sh` enabled for interactive Bash sessions |

**Additional system configuration:**
- `%_install_langs fr,en` configured in `/etc/rpm/macros.image-language-conf`.
- Automatic GNOME keyring unlocking (`login.keyring` without idle/after lock) configured for `ps5`.
- Custom PS5 kernel RPM installed (`/opt/rpms/*.rpm`), `depmod` run, and `/etc/kernel/postinst.d/zz-update-boot` invoked.
- Uncompressed AMD PS5 GPU firmware (`cyan_skillfish*`), GDM autologin, ZRAM swap, and SELinux disabled.

### 4.3 Test Build — Additional Features

| Component / Addition | Description |
| :--- | :--- |
| **RPM Fusion & Multimedia Codecs** | RPM Fusion Free/Nonfree enabled; `ffmpeg`, `ffmpeg-libs`, `gstreamer1-plugins-bad-freeworld`, and `gstreamer1-plugins-ugly` installed via `dnf` (`--allowerasing --skip-unavailable`) |
| **32-bit Graphics Libraries (`i686`)** | `mesa-vulkan-drivers.i686`, `mesa-dri-drivers.i686`, `libva.i686` installed via `dnf` |
| **Flathub & Extension Manager** | Flathub remote added; `com.mattjakeman.ExtensionManager` installed via Flatpak |
| **Balena Etcher** | Latest `x86_64.rpm` fetched from GitHub releases and installed via `dnf` |
| **ps5-linux-tools** | Cloned, compiled (`make`), and installed to `/usr/local/sbin/ps5_control` |
| **Decky Loader** | Installed for user `ps5` via `decky-installer` in `post-files` |
| **PS5 Fedora Manager** | Cloned from `nexgen999/ps5-fedora-manager` and installed via `./install.sh` |
| **PS5 Performance Service** | `ps5-performance.service` enabled (`--fan on` and `--boost on`) |
| **PS5 Internal WiFi** | `ps5-iw620.service`, `ps5-iw620-load`, and `ps5-iw620-noautoload.conf` configured and enabled |
| **Nautilus & Terminal Helpers** | Adds Nautilus script `"Ouvrir dans le terminal"` and helper `/home/ps5/.local/bin/open-term-here` (using `wl-paste`) |
| **Bash Completion** | Global profile script `/etc/profile.d/ps5-bash-completion.sh` enabled |

**Additional system configuration:**
- Services enabled: `sshd`, `NetworkManager`, `avahi-daemon`, `cups`, `gdm`, `bluetooth.service`, `grow-rootfs.service`, `ps5-performance.service`, `ps5-iw620.service`, and `graphical.target`.
- `%_install_langs fr,en` configured in `/etc/rpm/macros.image-language-conf`.
- GDM autologin, automatic GNOME keyring unlocking, ZRAM swap, SELinux disabled, and custom PS5 kernel installation.

---

## 5. Important Differences Between the Builds

| Feature | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| **Fedora 44** | ✅ | ❌ | ❌ |
| **Fedora 45** | ❌ | ✅ | ✅ |
| **GNOME Desktop** | ✅ | ✅ | ✅ |
| **Basic Bluetooth** | ✅ | ✅ | ✅ |
| **File sharing (SMB / NFS)** | ❌ | ✅ | ✅ |
| **Flatpak & Flathub** | ❌ | ✅ | ✅ |
| **RPM Fusion** | ❌ | ✅ | ✅ |
| **Development tools** | ❌ | Partial | Extended |
| **GTK4 / Libadwaita** | ❌ | ✅ | ✅ |
| **French localization (`fr`)** | ❌ | ✅ | ✅ |
| **Mobile connectivity packages** | ❌ | ❌ | ✅ |
| **Printing (`cups`) & Scanning (`sane`)** | ❌ | ❌ | ✅ |
| **Multimedia codecs (`ffmpeg` / GStreamer)** | ❌ | ❌ | ✅ |
| **32-bit graphics libraries (`i686`)** | ❌ | Script-installed | Script-installed |
| **Decky Loader & PS5 Fedora Manager** | ❌ | ✅ | ✅ |
| **Automatic PS5 performance service** | ❌ | ✅ | ✅ |
| **PS5 IW620 WiFi service (`ps5-iw620`)** | ✅ | ✅ | ✅ |
| **CUPS & Avahi automatic activation** | ❌ | ❌ | ✅ |

---

## 6. Overall Comparison

### PS5-Linux — Original Build
The original **PS5-Linux** build (Fedora 44) provides a minimal GNOME/Wayland baseline for the PS5. It includes core desktop, graphics, networking, and system packages, along with PS5 kernel integration, uncompressed AMD GPU firmware, and PS5 IW620 WiFi handling.

### PS5 Fedora Desktop Edition — Desktop Build
The **Desktop Edition** (Fedora 45) builds a lightweight everyday desktop environment (`Lightweight & Essential`). It adds SMB/NFS file sharing, GTK4/Libadwaita, Flatpak/Flathub, RPM Fusion, `fr`/`en` localization, 32-bit graphics libraries, Balena Etcher, Decky Loader, PS5 Fedora Manager, and the `ps5-performance` service.

### PS5 Fedora Test Build — Extended Build
The **Test Build** (Fedora 45) expands the desktop configuration (`Full Desktop + Mobile + Print/Scan + Codecs + Dev`). It adds extensive GNOME/GTK packages, multimedia packages and codecs (`ffmpeg`, GStreamer), mobile/device tools (`gsconnect`, `android-tools`, `fuse-sshfs`, `wl-clipboard`, `gvfs-*`), printing/scanning (`cups`, `sane`), a broader developer toolchain, Nautilus/terminal helper scripts, and automatic `avahi-daemon` and `cups` services.

---

## 7. Conclusion

| Build | Main Objective |
| :--- | :--- |
| **PS5-Linux** | Minimal Fedora 44 GNOME baseline for PS5 |
| **Desktop Edition** | Lightweight Fedora 45 desktop with PS5 management tools and everyday utilities |
| **Test Build** | Broad Fedora 45 test environment covering extended desktop, media, mobile, print/scan, and dev tools |

---

## 8. Comparison Methodology and Limitations

This comparison is based on the provided YAML definitions (`ps5-linux.yaml`, `fedora.45-desktop_edition.yaml`, and `fedora.45-test_build.yaml`).

- Explicitly listed `packages` may pull in additional dependencies automatically via DNF.
- Shell scripts in `actions` (`post-unpack`, `post-update`, `post-packages`, `post-files`) can install external RPMs/Flatpaks/tools, modify configs, or enable services outside the `packages` list.
- Build scripts and remote repositories referenced in `actions` (such as GitHub releases, RPM Fusion, or Flathub) can evolve over time.

*Last comparison reference: November 2026.*
