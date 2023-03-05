# Manjaro is stuck at load screen
Solution adapted from [here] (https://forum.manjaro.org/t/stuck-at-loading-screen-after-installing-proprietary-nvidia-drivers/133798/2)

1. boot from the live cd or usd to Manjaro
2. Run `kate /etc/default/grub` and modify the `GRUB_CMDLINE_LINUX_DEFAULT=""` to `RUB_CMDLINE_LINUX="ibt=off"` and save the file
3. update grub from terminal using: `sudo update-grub`
4. open `kate /etc/mkinitcpio.conf` and edit the module section to `MODULES=(i915 nvidia nvidia_drm nvidia_uvm nvidia_modeset)` and save the file.
5. update the mkinitcpio from the terminal using: `sudo mkinitcpio -P`
6. update your system: `sudo pacman-mirrors --fasttrack 5 && sudo pacman -Syyu`
7. install nvidia: `sudo mhwd -a pci nonfree 0300`
8. reboot! The system should work now
