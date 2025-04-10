# Broadcom Wi-Fi Service Patch for MacBook Pro 2011 on Ubuntu

On recent Ubuntu releases Broadcom Wi-Fi network card (installed on the MacBook Pro late 2011) does not work at all, as expected.
After reviewing various community solutions, I've developed a startup service that, upon boot, reinitializes kernel module for this network card.

## Prerequisites

Install Broadcom kernel source package:
```bash
sudo apt install bcmwl-kernel-source
```

## File Setup

Place these files in their respective locations (as positioned in this project).
You can also use your preferred text editor, such nano from terminal, to create or edit these files.

Then, make the bash script executable with:
```bash
sudo chmod +x /usr/local/bin/wifi-reset.sh
```

## Enabling service

Enable the service so it runs at every startup:
```bash
sudo systemctl enable wifi-startup.service
```

(Optional) To start service immediately without rebooting:
```bash
sudo systemctl start wifi-startup.service
```