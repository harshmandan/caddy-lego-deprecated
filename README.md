# caddy-lego-deprecated
Prebuilt caddy with lego-deprecated

# [Install](https://caddyserver.com/docs/install#debian-ubuntu-raspbian) default caddy
```
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```

# Set-up UFW
```
ufw allow 'OpenSSH'
ufw allow proto tcp from any to any port 80,443
ufw enable
```

# Create a `Caddyfile` in `/etc/caddy/`
Caddyfile configuration (gist)

# Set up DO sercret credentials in file: `/etc/systemd/system/caddy.service`
Secret token configuration (gist)

# Download from your terminal:
`wget https://github.com/harshmandan/caddy-lego-deprecated/releases/download/v2.4.0/caddy`

# Move file
`sudo mv caddy /usr/bin`

# Give permissions

```
sudo chown root:root /usr/bin/caddy
sudo chmod 755 /usr/bin/caddy
```

# Restart
```
sudo systemctl daemon-reload
sudo systemctl restart caddy
```

# To validate Caddyfile
```
caddy validate
```
