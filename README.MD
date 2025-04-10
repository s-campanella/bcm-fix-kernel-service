# Broadcom Wi-Fi Service Patch for MacBook Pro 2011 on Ubuntu

Recent Ubuntu releases have shown that the Broadcom Wi-Fi network card (installed on the MacBook Pro late 2011) doesn't work as expected. After reviewing various community solutions, I've developed a startup service that, upon boot, reinitializes the kernel module for the network card.

## Prerequisites

Install the Broadcom kernel source package:
```bash
sudo apt install bcmwl-kernel-source
```

## File Setup

Place these files in their respective locations. You can use your preferred text editor (e.g., via nano) to create or edit these files.

Them, make the script executable with:
```bash
sudo chmod +x /usr/local/bin/wifi-reset.sh
```

## Enabling the Service

Enable the service so it runs at startup:
```bash
sudo systemctl enable wifi-startup.service
```

(Optional) To start the service immediately without rebooting:
```bash
sudo systemctl start wifi-startup.service
```