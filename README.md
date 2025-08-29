# Dummy Service with systemd

This project demonstrates how to create a background Linux service using a bash script and `systemd`.

## Features
- Script (`dummy.sh`) writes logs every 10 seconds to `/var/log/dummy-service.log`
- `dummy.service` keeps the script running automatically on boot
- Auto-restarts if the process fails

## Usage
```bash
sudo systemctl start dummy
sudo systemctl status dummy
sudo systemctl enable dummy
sudo journalctl -u dummy -f

