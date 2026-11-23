# Builds Fedora PS5 — Comparaison complète des paquets

Ce document compare les trois builds Linux basés sur Fedora pour la PlayStation 5 en analysant leurs fichiers de configuration `image.yaml` respectifs.

**L'objectif est d'identifier :**
- Les paquets communs aux trois builds.
- Les paquets spécifiques à chaque build.
- Les paquets ajoutés entre le build original **PS5-Linux** et la **Desktop Edition** personnalisée.
- Les paquets supplémentaires introduits par la **Test Build**.
- Les différences de configuration système, de services et de scripts d'installation.

---

## 1. Dépôts sources

| Build | Dépôt / Fichier source | Version de Fedora |
| :--- | :--- | :---: |
| **PS5-Linux** | `ps5-linux-image` (`ps5-linux.yaml`) | Fedora 44 |
| **PS5 Fedora Desktop Edition** | `PS5-Fedora_Desktop-Edition` (`fedora.45-desktop_edition.yaml`) | Fedora 45 |
| **PS5 Fedora Test Build** | `PS5-Fedora_Test_Build` (`fedora.45-test_build.yaml`) | Fedora 45 |

**Les trois builds partagent la base suivante :**
- **Architecture :** `x86_64`
- **Gestionnaire de paquets :** DNF
- **Environnement de bureau :** GNOME
- **Protocole d'affichage :** Wayland
- **Gestionnaire de connexion :** GDM

---

## 2. Légende

| Symbole | Signification |
| :---: | :--- |
| ✅ | Explicitement inclus dans la section `packages` du build |
| ❌ | Non explicitement déclaré dans la section `packages` du build |

> **Important :** Cette comparaison couvre les paquets explicitement déclarés dans les listes `packages`. Les dépendances Fedora et les paquets/composants installés dynamiquement par les scripts de build (`actions`) sont documentés séparément dans la [Section 4](#4-installations-supplementaires-effectuees-par-les-scripts-de-build).

---

## 3. Comparaison des paquets

### 3.1 Environnement de bureau GNOME

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

| Paquet | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `bluez` | ✅ | ✅ | ✅ |
| `bluez-tools` | ✅ | ✅ | ✅ |
| `gnome-bluetooth` | ❌ | ❌ | ✅ |

### 3.3 Audio et multimédia

| Paquet | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `pipewire` | ✅ | ✅ | ✅ |
| `wireplumber` | ✅ | ✅ | ✅ |
| `pipewire-pulseaudio` | ✅ | ✅ | ✅ |
| `gstreamer1-plugins-base` | ❌ | ❌ | ✅ |
| `gstreamer1-plugins-good` | ❌ | ❌ | ✅ |
| `gstreamer1-plugins-bad-free` | ❌ | ❌ | ✅ |
| `gstreamer1-plugins-ugly-free` | ❌ | ❌ | ✅ |
| `gstreamer1-libav` | ❌ | ❌ | ✅ |

### 3.4 Graphismes et GPU

| Paquet | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `mesa-dri-drivers` | ✅ | ✅ | ✅ |
| `mesa-libEGL` | ❌ | ❌ | ✅ |
| `mesa-vulkan-drivers` | ✅ | ✅ | ✅ |
| `mesa-va-drivers` | ✅ | ✅ | ✅ |
| `vulkan-tools` | ❌ | ✅ | ✅ |
| `mesa-demos` | ❌ | ✅ | ✅ |
| `libinput` | ✅ | ✅ | ✅ |

### 3.5 Réseau et partage de fichiers

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

### 3.6 Connectivité mobile

| Paquet | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `gnome-shell-extension-gsconnect` | ❌ | ❌ | ✅ |
| `fuse-sshfs` | ❌ | ❌ | ✅ |
| `nautilus-python` | ❌ | ❌ | ✅ |
| `android-tools` | ❌ | ❌ | ✅ |
| `wl-clipboard` | ❌ | ❌ | ✅ |

### 3.7 Impression et numérisation

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

### 3.8 Outils de développement

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

### 3.9 GTK4 et Libadwaita

| Paquet | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| `python3-gobject` | ❌ | ✅ | ✅ |
| `gtk4` | ❌ | ✅ | ✅ |
| `libadwaita` | ❌ | ✅ | ✅ |
| `gobject-introspection` | ❌ | ✅ | ✅ |
| `desktop-file-utils` | ❌ | ✅ | ✅ |
| `xhost` | ❌ | ✅ | ✅ |

### 3.10 Localisation et saisie

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

### 3.11 Système de base et utilitaires

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

### 3.12 Polices d'écriture

| Paquet | PS5-Linux | Desktop Edition | Test Build |
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

## 4. Installations supplémentaires effectuées par les scripts de build

Certains logiciels et configurations sont appliqués via des scripts shell personnalisés (`actions`) plutôt que dans la section `packages`.

### 4.1 PS5-Linux

- **Paquets / fichiers installés via scripts :** RPM du noyau Linux PS5 personnalisé (`/opt/rpms/*.rpm`), firmware GPU AMD PS5 décompressé (`cyan_skillfish*`), et préparation du firmware WiFi PS5 IW620 (`/usr/local/sbin/ps5-iw620-load`).
- **Services activés / configurés :** `sshd`, `NetworkManager`, `gdm`, `bluetooth.service`, `grow-rootfs.service`, `ps5-iw620.service` et `graphical.target`.
- **Configuration système :** mot de passe `root` verrouillé (`passwd -l root`), utilisateur `ps5` créé (`wheel,video,input,render` avec `sudo` sans mot de passe), connexion automatique GDM activée pour `ps5`, `gnome-initial-setup` ignoré pour `ps5`, swap ZRAM (`zram0`, `ram / 2`, `zstd`), SELinux désactivé, `retries=10` dans `/etc/dnf/dnf.conf`.

### 4.2 Desktop Edition — Fonctionnalités supplémentaires

| Composant / Ajout | Description |
| :--- | :--- |
| **RPM Fusion Free & Nonfree** | Installés via `dnf` dans `post-packages` avec `rpmfusion-free-release` et `rpmfusion-nonfree-release` |
| **Bibliothèques graphiques 32 bits (`i686`)** | `mesa-vulkan-drivers.i686`, `mesa-dri-drivers.i686`, `libva.i686` installés via `dnf` dans `post-packages` |
| **Flathub & Extension Manager** | Dépôt Flathub ajouté ; `com.mattjakeman.ExtensionManager` installé via Flatpak |
| **Balena Etcher** | Dernier `x86_64.rpm` récupéré depuis les releases GitHub et installé via `dnf` |
| **ps5-linux-tools** | Cloné, compilé (`make`) et installé dans `/usr/local/sbin/ps5_control` |
| **Decky Loader** | Installé pour l'utilisateur `ps5` via `decky-installer` dans `post-files` |
| **PS5 Fedora Manager** | Cloné depuis `nexgen999/ps5-fedora-manager` et installé via `./install.sh` |
| **Service de performance PS5** | `ps5-performance.service` activé pour exécuter `ps5_control --fan on` et `--boost on` |
| **WiFi interne PS5** | `ps5-iw620.service`, `ps5-iw620-load` et `ps5-iw620-noautoload.conf` configurés et activés |
| **Bash Completion** | Script global `/etc/profile.d/ps5-bash-completion.sh` activé pour les sessions Bash interactives |

**Configuration système supplémentaire :**
- `%_install_langs fr,en` configuré dans `/etc/rpm/macros.image-language-conf`.
- Déverrouillage automatique du trousseau GNOME (`login.keyring` sans verrouillage à l'inactivité ou après délai) configuré pour `ps5`.
- RPM du noyau PS5 personnalisé installé (`/opt/rpms/*.rpm`), `depmod` exécuté et `/etc/kernel/postinst.d/zz-update-boot` appelé.
- Firmware GPU AMD PS5 décompressé (`cyan_skillfish*`), connexion automatique GDM, swap ZRAM et SELinux désactivé.

### 4.3 Test Build — Fonctionnalités supplémentaires

| Composant / Ajout | Description |
| :--- | :--- |
| **RPM Fusion & Codecs multimédias** | RPM Fusion Free/Nonfree activés ; `ffmpeg`, `ffmpeg-libs`, `gstreamer1-plugins-bad-freeworld` et `gstreamer1-plugins-ugly` installés via `dnf` (`--allowerasing --skip-unavailable`) |
| **Bibliothèques graphiques 32 bits (`i686`)** | `mesa-vulkan-drivers.i686`, `mesa-dri-drivers.i686`, `libva.i686` installés via `dnf` |
| **Flathub & Extension Manager** | Dépôt Flathub ajouté ; `com.mattjakeman.ExtensionManager` installé via Flatpak |
| **Balena Etcher** | Dernier `x86_64.rpm` récupéré depuis les releases GitHub et installé via `dnf` |
| **ps5-linux-tools** | Cloné, compilé (`make`) et installé dans `/usr/local/sbin/ps5_control` |
| **Decky Loader** | Installé pour l'utilisateur `ps5` via `decky-installer` dans `post-files` |
| **PS5 Fedora Manager** | Cloné depuis `nexgen999/ps5-fedora-manager` et installé via `./install.sh` |
| **Service de performance PS5** | `ps5-performance.service` activé (`--fan on` et `--boost on`) |
| **WiFi interne PS5** | `ps5-iw620.service`, `ps5-iw620-load` et `ps5-iw620-noautoload.conf` configurés et activés |
| **Scripts Nautilus & Terminal** | Ajoute le script Nautilus `"Ouvrir dans le terminal"` et l'utilitaire `/home/ps5/.local/bin/open-term-here` (avec `wl-paste`) |
| **Bash Completion** | Script global `/etc/profile.d/ps5-bash-completion.sh` activé |

**Configuration système supplémentaire :**
- Services activés : `sshd`, `NetworkManager`, `avahi-daemon`, `cups`, `gdm`, `bluetooth.service`, `grow-rootfs.service`, `ps5-performance.service`, `ps5-iw620.service` et `graphical.target`.
- `%_install_langs fr,en` configuré dans `/etc/rpm/macros.image-language-conf`.
- Connexion automatique GDM, déverrouillage automatique du trousseau GNOME, swap ZRAM, SELinux désactivé et installation du noyau PS5 personnalisé.

---

## 5. Différences importantes entre les builds

| Fonctionnalité | PS5-Linux | Desktop Edition | Test Build |
| :--- | :---: | :---: | :---: |
| **Fedora 44** | ✅ | ❌ | ❌ |
| **Fedora 45** | ❌ | ✅ | ✅ |
| **Bureau GNOME** | ✅ | ✅ | ✅ |
| **Bluetooth de base** | ✅ | ✅ | ✅ |
| **Partage de fichiers (SMB / NFS)** | ❌ | ✅ | ✅ |
| **Flatpak & Flathub** | ❌ | ✅ | ✅ |
| **RPM Fusion** | ❌ | ✅ | ✅ |
| **Outils de développement** | ❌ | Partiel | Étendu |
| **GTK4 / Libadwaita** | ❌ | ✅ | ✅ |
| **Localisation française (`fr`)** | ❌ | ✅ | ✅ |
| **Paquets de connectivité mobile** | ❌ | ❌ | ✅ |
| **Impression (`cups`) & Numérisation (`sane`)** | ❌ | ❌ | ✅ |
| **Codecs multimédias (`ffmpeg` / GStreamer)** | ❌ | ❌ | ✅ |
| **Bibliothèques graphiques 32 bits (`i686`)** | ❌ | Via script | Via script |
| **Decky Loader & PS5 Fedora Manager** | ❌ | ✅ | ✅ |
| **Service automatique de performance PS5** | ❌ | ✅ | ✅ |
| **Service WiFi PS5 IW620 (`ps5-iw620`)** | ✅ | ✅ | ✅ |
| **Activation automatique de CUPS & Avahi** | ❌ | ❌ | ✅ |

---

## 6. Comparaison globale

### PS5-Linux — Build original
Le build original **PS5-Linux** (Fedora 44) fournit une base minimale GNOME/Wayland pour la PS5. Il inclut les paquets essentiels de bureau, graphismes, réseau et système, ainsi que l'intégration du noyau PS5, le firmware GPU AMD décompressé et la gestion du WiFi PS5 IW620.

### PS5 Fedora Desktop Edition — Build bureau
La **Desktop Edition** (Fedora 45) constitue un environnement de bureau léger pour un usage quotidien (`Lightweight & Essential`). Elle ajoute le partage de fichiers SMB/NFS, GTK4/Libadwaita, Flatpak/Flathub, RPM Fusion, la localisation `fr`/`en`, les bibliothèques graphiques 32 bits, Balena Etcher, Decky Loader, PS5 Fedora Manager et le service `ps5-performance`.

### PS5 Fedora Test Build — Build étendue
La **Test Build** (Fedora 45) élargit la configuration de bureau (`Full Desktop + Mobile + Print/Scan + Codecs + Dev`). Elle ajoute de nombreux paquets GNOME/GTK, des paquets et codecs multimédias (`ffmpeg`, GStreamer), des outils mobiles/périphériques (`gsconnect`, `android-tools`, `fuse-sshfs`, `wl-clipboard`, `gvfs-*`), l'impression/numérisation (`cups`, `sane`), une chaîne d'outils de développement plus complète, des scripts Nautilus/terminal ainsi que l'activation automatique d'`avahi-daemon` et de `cups`.

---

## 7. Conclusion

| Build | Objectif principal |
| :--- | :--- |
| **PS5-Linux** | Base minimale Fedora 44 GNOME pour PS5 |
| **Desktop Edition** | Bureau léger Fedora 45 avec outils de gestion PS5 et utilitaires du quotidien |
| **Test Build** | Environnement de test complet Fedora 45 couvrant bureau étendu, multimédia, mobile, impression/scan et développement |

---

## 8. Méthodologie et limites de la comparaison

Cette comparaison repose sur les définitions YAML fournies (`ps5-linux.yaml`, `fedora.45-desktop_edition.yaml` et `fedora.45-test_build.yaml`).

- Les paquets listés dans `packages` peuvent installer automatiquement des dépendances supplémentaires via DNF.
- Les scripts shell dans `actions` (`post-unpack`, `post-update`, `post-packages`, `post-files`) peuvent installer des RPM/Flatpaks/outils externes, modifier des configurations ou activer des services en dehors de la liste `packages`.
- Les scripts de build et dépôts distants référencés dans `actions` (comme les releases GitHub, RPM Fusion ou Flathub) peuvent évoluer dans le temps.

*Dernière référence de comparaison : novembre 2026.*
