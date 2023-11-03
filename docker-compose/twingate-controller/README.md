# systemd service


Add a systemd service like /etc/systemd/system/twingate-controller.service

```
[Unit]
Description=TWINGATE CONTROLLER

[Service]
WorkingDirectory=/home/[user]/twingate-controller
ExecStartPre=/snap/bin/docker-compose down
ExecStart=/snap/bin/docker-compose up
ExecStop=/snap/bin/docker-compose  down
TimeoutStartSec=0
Restart=on-failure
StartLimitIntervalSec=60
StartLimitBurst=3

[Install]
WantedBy=multi-user.target
```



Enable service by:
sudo systemctl enable twingate-controller
