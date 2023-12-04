# PI Led Strip
Control WS2811 indexable led strip over WiFi using a self hosted web page.

# Service setup
The following block is a service configuration file (`service_name.service`) example. `ExecStart` must be an executable program, you can set it up like this: `sudo chmod +x program.py`.

```bash
[Unit]
Description=Service description

[Service]
Type=simple
User=pi
WorkingDirectory=/home/pi/Github/repo/main
ExecStart=/home/pi/Github/repo/main/./program.py
TimeoutSec=45s
Restart=always
RestartSec=20s

[Install]
WantedBy=multi-user.target
```

Here are some useful commads to set up the service vonfigured below.
```bash
# Symlink the service configuration to the default service location.
sudo ln -s /home/pi/Github/repo/services/service_name.service /etc/systemd/system

# Enable service (starts service automatically)
sudo systemctl enable service_name

# Disable service
sudo systemctl disable service_name

# Start service
sudo systemctl start service_name
sudo systemctl status service_name

# Stop service
sudo systemctl stop service_name
sudo systemctl status service_name

# Show services journal
sudo journalctl -f
```
