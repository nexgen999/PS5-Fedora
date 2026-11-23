# Récapitulatif des ajouts — Build de test Fedora 45 GNOME (PS5)

Ce document liste l'ensemble des paquets, codecs, outils, scripts et réglages ajoutés autour de ta base `image.yaml` pour la build de test orientée « système complet par défaut ».

---

## 1. Applications, aperçus et utilitaires GNOME
* **Média & aperçus** : `sushi` (aperçu rapide dans *Fichiers*), `showtime` (lecteur vidéo), `decibels` (lecteur audio), `snapshot` (caméra), `gst-thumbnailers`, `glycin-thumbnailer`.
* **Documents & fichiers** : `papers`, `papers-nautilus`, `gnome-epub-thumbnailer`, `gnome-font-viewer`, `librsvg2`.
* **Bureau, réseau & système** : `gnome-classic-session`, `gnome-boxes`, `gnome-calendar`, `gnome-characters`, `gnome-clocks`, `gnome-color-manager`, `gnome-connections`, `gnome-contacts`, `gnome-logs`, `gnome-maps`, `gnome-remote-desktop`, `gnome-user-docs`, `gnome-user-share`, `gnome-weather`, `rygel`, `localsearch`, `tinysparql`, `vte-profile`, `xdg-desktop-portal`, `xdg-desktop-portal-gtk`, `gnome-browser-connector`, `yelp`, `toolbox`, `systemd-oomd-defaults`, `fprintd-pam`, `glib-networking`, `PackageKit-command-not-found`, `PackageKit-gtk3-module`, `mesa-libEGL`, `gnome-bluetooth`, `avahi`.

---

## 2. Connectivité mobile et utilitaires presse-papier / fichiers
* **GSConnect & Android** : `gnome-shell-extension-gsconnect`, `android-tools` (`adb` et `fastboot`), `gvfs-mtp` (déjà présent dans ta base, conservé), `gvfs-afc`, `gvfs-goa`, `gvfs-gphoto2`.
* **Systèmes de fichiers distants & extensions Nautilus** : `fuse-sshfs`, `nautilus-python`.
* **Presse-papier Wayland** : `wl-clipboard` (`wl-paste` utilisé par le lanceur de dossier).

---

## 3. Impression (CUPS) et numérisation (SANE)
* **Impression** : `cups`, `cups-filters`, `system-config-printer`, `hplip`, `gutenprint-cups`, `splix`.
* **Numérisation** : `sane-backends`, `sane-backends-drivers-scanners`, `libsane-hpaio`, `simple-scan`.
* **Service** : activation de `cups` (`systemctl enable cups`, ou `sudo systemctl disable --now cups` / `cups.socket` / `cups.path` pour le couper).

---

## 4. Codecs multimédia et RPM Fusion
* **GStreamer (base / officiel Fedora)** : `gstreamer1-plugins-base`, `gstreamer1-plugins-good`, `gstreamer1-plugins-bad-free`, `gstreamer1-plugins-ugly-free`, `gstreamer1-libav`.
* **RPM Fusion (`free` / `nonfree`) & FFmpeg** : activation des dépôts RPM Fusion et installation (en `post-packages` avec tolérance `--allowerasing --skip-unavailable` pour éviter de bloquer la phase `packages:`) de `ffmpeg`, `ffmpeg-libs`, `gstreamer1-plugins-bad-freeworld` et `gstreamer1-plugins-ugly`.

---

## 5. Outils de développement et compilation
En complément de `git`, `make` et `gcc` déjà présents :
* **Compilateurs & outils de build** : `gcc-c++`, `gdb`, `cmake`, `ninja-build`, `meson`, `autoconf`, `automake`, `libtool`, `patch`, `binutils`, `pkgconf`, `pkgconf-pkg-config`, `rpm-build`.
* **Python** : `python3-pip`, `python3-pyyaml`.

---

## 6. Scripts Nautilus et ouverture de terminal dans le dossier
* **Script Nautilus** : `/home/ps5/.local/share/nautilus/scripts/Ouvrir dans le terminal` (exécutable `0755`, propriété `ps5:ps5` ; visible dans le menu *Scripts* lorsqu'un élément est sélectionné dans *Fichiers*).
* **Lanceur dossier courant / presse-papier** : `/home/ps5/.local/bin/open-term-here` (exécutable `0755`, propriété `ps5:ps5` ; ouvre `gnome-terminal --working-directory` sur l'argument passé ou sur le chemin copié dans le presse-papier via `wl-paste`, avec repli sur `$HOME`).
