# glance-template

Yam Custom template for Glance Dashboard

# Getting started

### Install template

```bash
cd /opt/glance
rm glance.yml
git clone https://github.com/amkac/glance-template.git
```

crate **prod.env** file, then configure token for your servcies.

```
# Poxmox conf
PROXMOX_IP=...
PROXMOX_PORT=...
PROXMOX_TOKEN=...
```

### Change glance systemd service

```bash
nano /etc/systemd/system/glance.service

```

Update in [Service] category

```
ExecStart=/opt/glance/glance --config /opt/glance/glance-template/glance.yml
EnvironmentFile=/opt/glance/glance-template/prod.env
```

Then restart daemon

```
systemctl daemon-reload
systemctl restart glance
systemctl status glance
```
