Fedora PS5 Builds — Complete Package Comparison

This document compares the three Fedora-based PlayStation 5 Linux builds by examining their respective image.yaml configuration files.

The objective is to identify:

Packages shared by all three builds.
Packages specific to each build.
Packages added between the original PS5-Linux build and the custom Desktop Edition.
Additional packages introduced by the Test Build.
Differences in system configuration, services and installation scripts.
1. Source repositories
Build	Repository	Fedora version
PS5-Linux	ps5-linux-image	Fedora 44
PS5 Fedora Desktop Edition	PS5-Fedora_Desktop-Edition	Fedora 45
PS5 Fedora Test Build	PS5-Fedora_Test_Build	Fedora 45

All three builds use:

Architecture: x86_64
Package manager: DNF
Desktop environment: GNOME
Display protocol: Wayland
Display manager: GDM
2. Legend
Symbol	Meaning
✅	Explicitly included in the build
❌	Not explicitly included in the package list

Important: This comparison covers explicitly declared packages. Fedora dependencies and packages installed dynamically by build scripts are documented separately.

3. Package comparison
3.1 GNOME Desktop Environment
Package	PS5-Linux	Desktop Edition	Test Build
gnome-shell	✅	✅	✅
gnome-session	✅	✅	✅
gnome-classic-session	❌	❌	✅
gnome-terminal	✅	✅	✅
gdm	✅	✅	✅
mutter	✅	✅	✅
nautilus	✅	✅	✅
gnome-control-center	✅	✅	✅
gnome-settings-daemon	✅	✅	✅
gnome-keyring	✅	✅	✅
seahorse	❌	✅	✅
pinentry-gnome3	❌	✅	✅
xdg-utils	❌	✅	✅
xdg-desktop-portal	❌	❌	✅
xdg-desktop-portal-gnome	✅	✅	✅
xdg-desktop-portal-gtk	❌	❌	✅
xdg-user-dirs-gtk	✅	✅	✅
gvfs	❌	✅	✅
gvfs-smb	❌	✅	✅
gvfs-nfs	❌	✅	✅
gvfs-fuse	❌	✅	✅
gvfs-mtp	❌	❌	✅
gvfs-afc	❌	❌	✅
gvfs-goa	❌	❌	✅
gvfs-gphoto2	❌	❌	✅
gnome-backgrounds	✅	✅	✅
gnome-text-editor	✅	✅	✅
gnome-system-monitor	✅	✅	✅
gnome-disk-utility	✅	✅	✅
gnome-calculator	✅	✅	✅
gnome-tweaks	✅	✅	✅
gnome-extensions-app	✅	✅	✅
gnome-software	✅	✅	✅
gnome-initial-setup	✅	✅	✅
gnome-boxes	❌	❌	✅
gnome-calendar	❌	❌	✅
gnome-characters	❌	❌	✅
gnome-clocks	❌	❌	✅
gnome-color-manager	❌	❌	✅
gnome-connections	❌	❌	✅
gnome-contacts	❌	❌	✅
gnome-epub-thumbnailer	❌	❌	✅
gnome-font-viewer	❌	❌	✅
gnome-logs	❌	❌	✅
gnome-maps	❌	❌	✅
gnome-remote-desktop	❌	❌	✅
gnome-user-docs	❌	❌	✅
gnome-user-share	❌	❌	✅
gnome-weather	❌	❌	✅
file-roller	✅	✅	✅
loupe	✅	✅	✅
evince	✅	✅	❌
papers	❌	❌	✅
papers-nautilus	❌	❌	✅
baobab	✅	✅	✅
sushi	❌	❌	✅
showtime	❌	❌	✅
decibels	❌	❌	✅
snapshot	❌	❌	✅
rygel	❌	❌	✅
localsearch	❌	❌	✅
tinysparql	❌	❌	✅
glycin-thumbnailer	❌	❌	✅
gst-thumbnailers	❌	❌	✅
librsvg2	❌	❌	✅
vte-profile	❌	❌	✅
gnome-browser-connector	❌	❌	✅
yelp	❌	❌	✅
toolbox	❌	❌	✅
systemd-oomd-defaults	❌	❌	✅
fprintd-pam	❌	❌	✅
glib-networking	❌	❌	✅
PackageKit-command-not-found	❌	❌	✅
PackageKit-gtk3-module	❌	❌	✅
xorg-x11-server-Xwayland	✅	✅	✅
polkit	✅	✅	✅
3.2 Bluetooth
Package	PS5-Linux	Desktop Edition	Test Build
bluez	✅	✅	✅
bluez-tools	✅	✅	✅
gnome-bluetooth	❌	❌	✅
3.3 Audio and Multimedia
Package	PS5-Linux	Desktop Edition	Test Build
pipewire	✅	✅	✅
wireplumber	✅	✅	✅
pipewire-pulseaudio	✅	✅	✅
gstreamer1-plugins-base	❌	❌	✅
gstreamer1-plugins-good	❌	❌	✅
gstreamer1-plugins-bad-free	❌	❌	✅
gstreamer1-plugins-ugly-free	❌	❌	✅
gstreamer1-libav	❌	❌	✅
3.4 Graphics and GPU
Package	PS5-Linux	Desktop Edition	Test Build
mesa-dri-drivers	✅	✅	✅
mesa-libEGL	❌	❌	✅
mesa-vulkan-drivers	✅	✅	✅
mesa-va-drivers	✅	✅	✅
vulkan-tools	❌	✅	✅
mesa-demos	❌	✅	✅
libinput	✅	✅	✅
3.5 Networking and File Sharing
Package	PS5-Linux	Desktop Edition	Test Build
NetworkManager	✅	✅	✅
NetworkManager-wifi	✅	✅	✅
network-manager-applet	✅	✅	✅
ModemManager	❌	❌	✅
NetworkManager-adsl	❌	❌	✅
NetworkManager-libreswan-gnome	❌	❌	✅
NetworkManager-openconnect-gnome	❌	❌	✅
NetworkManager-openvpn-gnome	❌	❌	✅
NetworkManager-ppp	❌	❌	✅
NetworkManager-ssh-gnome	❌	❌	✅
NetworkManager-wwan	❌	❌	✅
avahi	❌	❌	✅
linux-firmware	✅	✅	✅
iw	✅	✅	✅
wpa_supplicant	✅	✅	✅
wireless-regdb	✅	✅	✅
cifs-utils	❌	✅	✅
samba-client	❌	✅	✅
samba	❌	✅	✅
nfs-utils	❌	✅	✅
ethtool	❌	✅	✅
nmap-ncat	❌	✅	✅
bind-utils	❌	✅	✅
curl	❌	✅	✅
wget	❌	✅	✅
pciutils	❌	✅	✅
usbutils	❌	✅	✅
util-linux	✅	✅	✅
3.6 Mobile Connectivity
Package	PS5-Linux	Desktop Edition	Test Build
gnome-shell-extension-gsconnect	❌	❌	❌
fuse-sshfs	❌	❌	❌
nautilus-python	❌	❌	❌
android-tools	❌	❌	❌
wl-clipboard	❌	❌	❌

Note: The Test Build includes mobile connectivity functionality through additional services and configuration only where explicitly installed. The packages listed above are not declared in the supplied package list.

3.7 Printing and Scanning
Package	PS5-Linux	Desktop Edition	Test Build
cups	❌	❌	✅
cups-filters	❌	❌	✅
system-config-printer	❌	❌	✅
hplip	❌	❌	✅
gutenprint-cups	❌	❌	✅
splix	❌	❌	✅
sane-backends	❌	❌	✅
sane-backends-drivers-scanners	❌	❌	✅
libsane-hpaio	❌	❌	✅
simple-scan	❌	❌	✅
3.8 Development Tools
Package	PS5-Linux	Desktop Edition	Test Build
git	❌	✅	❌
make	❌	✅	❌
gcc	❌	✅	❌
gcc-c++	❌	❌	✅
gdb	❌	❌	✅
cmake	❌	❌	✅
ninja-build	❌	❌	✅
meson	❌	❌	✅
autoconf	❌	❌	✅
automake	❌	❌	✅
libtool	❌	❌	✅
patch	❌	❌	✅
binutils	❌	❌	✅
pkgconf	❌	❌	✅
pkgconf-pkg-config	❌	❌	✅
rpm-build	❌	❌	✅
python3-pip	❌	❌	✅
python3-pyyaml	❌	❌	✅
zlib-devel	❌	✅	✅
python3-PyQt6	❌	✅	✅
3.9 GTK4 and Libadwaita
Package	PS5-Linux	Desktop Edition	Test Build
python3-gobject	❌	✅	✅
gtk4	❌	✅	✅
libadwaita	❌	✅	✅
gobject-introspection	❌	✅	✅
desktop-file-utils	❌	✅	✅
xhost	❌	✅	✅
3.10 Localization and Input
Package	PS5-Linux	Desktop Edition	Test Build
glibc-langpack-en	✅	❌	❌
glibc-all-langpacks	❌	✅	✅
langpacks-fr	❌	✅	✅
langpacks-en	❌	✅	✅
firefox-langpacks	❌	✅	✅
xkeyboard-config	❌	✅	✅
ibus	❌	✅	✅
ibus-gtk3	❌	✅	✅
ibus-gtk4	❌	✅	✅
3.11 Base System and Utilities
Package	PS5-Linux	Desktop Edition	Test Build
bash-completion	❌	✅	✅
zenity	❌	✅	✅
newt	❌	✅	✅
openssh-server	✅	✅	✅
sudo	✅	✅	✅
nano	✅	✅	✅
dracut	✅	✅	✅
kmod	✅	✅	✅
e2fsprogs	✅	✅	✅
parted	✅	✅	✅
cloud-utils-growpart	✅	✅	✅
kexec-tools	✅	✅	✅
zram-generator-defaults	✅	✅	✅
firefox	✅	✅	✅
flatpak	❌	✅	✅
fuse	❌	✅	✅
fuse-libs	❌	✅	✅
3.12 Fonts
Package	PS5-Linux	Desktop Edition	Test Build
dejavu-sans-fonts	✅	✅	✅
liberation-fonts	✅	✅	✅
adobe-source-code-pro-fonts	❌	❌	✅
google-noto-sans-fonts	✅	❌	❌
google-noto-emoji-fonts	✅	❌	❌
google-noto-color-emoji-fonts	❌	✅	✅
google-noto-sans-symbols-fonts	❌	✅	✅
fontconfig	✅	✅	✅
4. Additional installations performed by build scripts

Some software is installed through custom shell scripts rather than the packages section. These installations must also be considered when comparing the final systems.

4.1 PS5-Linux

The original build includes:

Custom PS5 Linux kernel RPM.
AMD PS5 GPU firmware decompression.
GNOME desktop configuration.
GDM automatic login.
SSH server configuration.
Bluetooth service activation.
NetworkManager activation.
Automatic root filesystem expansion.
ZRAM swap configuration.
SELinux disabled.
4.2 Desktop Edition — Additional Features

The Desktop Edition introduces several additional components:

Component	Description
RPM Fusion Free	Additional Fedora software repository
RPM Fusion Nonfree	Additional non-free software repository
Flathub	Flatpak application repository
Flatpak Extension Manager	GNOME extension management
Balena Etcher	USB and storage image flashing utility
ps5-linux-tools	PS5-specific management utilities
PS5 Fedora Manager	Custom Fedora management application
GTK4	Modern graphical toolkit
Libadwaita	GNOME application design library
Bash Completion	Improved terminal command completion
32-bit Mesa Vulkan	32-bit Vulkan graphics libraries
32-bit Mesa DRI	32-bit OpenGL graphics libraries
32-bit libva	32-bit video acceleration library

Additional system configuration:

Automatic GNOME login.
Automatic GNOME keyring unlocking.
PS5 fan control.
PS5 performance boost activation.
Automatic PS5 performance systemd service.
Automatic filesystem expansion.
Custom PS5 kernel installation.
AMD PS5 firmware decompression.
4.3 Test Build — Additional Features

The Test Build expands the Desktop Edition with a broader collection of desktop and system functionality.

Component	Description
GStreamer plugins	Additional multimedia support
FFmpeg	Multimedia encoding and decoding
RPM Fusion Free	Additional Fedora repository
RPM Fusion Nonfree	Additional non-free repository
Flathub	Flatpak application repository
Balena Etcher	Image flashing utility
Extension Manager	GNOME extension management
ps5-linux-tools	PS5-specific utilities
32-bit Mesa Vulkan	32-bit graphics support
32-bit Mesa DRI	32-bit OpenGL support
32-bit libva	32-bit video acceleration
CUPS	Printing system
Avahi	Local network service discovery
Scanner backends	Scanner compatibility
Additional GNOME applications	Expanded desktop environment
Additional developer toolchain	Compilation and debugging tools

Additional system configuration:

Automatic GNOME login.
Automatic GNOME keyring unlocking.
Automatic filesystem expansion.
Custom PS5 kernel installation.
AMD PS5 firmware decompression.
Automatic SSH activation.
Automatic NetworkManager activation.
Automatic Avahi activation.
Automatic CUPS activation.
French and English localization.
RPM language configuration restricted to French and English.
5. Important differences between the builds
Feature	PS5-Linux	Desktop Edition	Test Build
Fedora 44	✅	❌	❌
Fedora 45	❌	✅	✅
GNOME Desktop	✅	✅	✅
Basic Bluetooth	✅	✅	✅
File sharing	❌	✅	✅
Samba / SMB	❌	✅	✅
NFS	❌	✅	✅
Flatpak	❌	✅	✅
Flathub	❌	✅	✅
RPM Fusion	❌	✅	✅
Development tools	❌	Partial	Extended
GTK4 / Libadwaita	❌	✅	✅
French localization	❌	✅	✅
Additional GNOME applications	❌	❌	✅
Multimedia codecs	❌	Partial	Extended
Printing	❌	❌	✅
Scanning	❌	❌	✅
32-bit graphics libraries	❌	Dynamically installed	Dynamically installed
PS5 management tools	Kernel integration	✅	✅
Automatic PS5 performance service	Not explicitly declared	✅	Not confirmed by the inspected configuration
CUPS automatic activation	❌	❌	✅
Avahi automatic activation	❌	❌	✅
6. Overall comparison
PS5-Linux — Original Build

The original PS5-Linux image focuses on providing a functional Fedora GNOME environment for the PlayStation 5.

Its main characteristics are:

Minimal desktop-oriented package selection.
Essential graphics and networking packages.
Basic system utilities.
PS5-specific kernel and firmware integration.

It provides the foundation for the other builds.

PS5 Fedora Desktop Edition — Desktop Build

The Desktop Edition expands the original image into a more complete desktop operating system.

Its main additions include:

File sharing and network utilities.
GTK4 and Libadwaita.
Flatpak and Flathub.
RPM Fusion repositories.
French and English localization.
Additional development dependencies.
Balena Etcher.
PS5 Fedora Manager.
PS5 performance management.

It aims to provide a practical everyday desktop experience while keeping the package selection relatively lightweight.

PS5 Fedora Test Build — Extended Build

The Test Build takes the Desktop Edition further by introducing a significantly larger software selection.

Its main additions include:

A considerably expanded GNOME environment.
Additional multimedia applications.
GStreamer and FFmpeg support.
Additional networking capabilities.
Android and mobile connectivity packages.
Printing and scanning support.
A more complete development toolchain.
Additional fonts and desktop utilities.

It is intended to provide a comprehensive environment for testing a wider range of desktop and hardware functionality.

7. Conclusion

The three builds follow different objectives:

Build	Main Objective
PS5-Linux	Basic Fedora GNOME environment for PS5
Desktop Edition	Lightweight and practical desktop experience
Test Build	Extended desktop with multimedia, printing, scanning and development capabilities

The Desktop Edition represents an evolution of the original PS5-Linux image, while the Test Build explores a much broader software configuration.

The Test Build is therefore the most feature-rich configuration in terms of explicitly declared packages and additional system functionality.

8. Comparison methodology and limitations

This document is based on the following source files:

PS5-Linux image.yaml
Desktop Edition image.yaml
Test Build image.yaml

The comparison distinguishes between:

Packages explicitly declared in the YAML package lists.
Software installed dynamically through build scripts.
Services enabled during image creation.
Configuration files and custom system modifications.

A package marked as absent does not necessarily mean that it cannot exist on the final system. It may be installed as a dependency or through a separate installation script.

Repository branches and configuration files can change over time. This document should be updated whenever the source builds are modified.

Last comparison reference: November 2026.
