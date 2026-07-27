# Firewall

## Description
This project covers configuring a firewall using UFW (Uncomplicated Firewall) on
an Ubuntu server to restrict incoming network traffic to only the ports required
for the web infrastructure to function.

## Background
By default, a server with no firewall accepts incoming traffic on every open
port. This project sets up UFW on `web-01` to block all incoming traffic except
for the ports needed to serve web and SSH traffic.

## Requirements
- Ubuntu 20.04 LTS
- UFW (Uncomplicated Firewall)

## Tasks

### 0. Block all incoming traffic but
File: [`0-block_all_incoming_traffic_but`](./0-block_all_incoming_traffic_but)

Configures UFW on `web-01` to block all incoming traffic except on the
following TCP ports:
- `22` (SSH)
- `80` (HTTP)
- `443` (HTTPS/SSL)

**Commands used:**
```bash
sudo apt update
sudo apt install ufw -y
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable
```

**Verification:**
Tested from `web-02` (outside the school network) using `telnet`:
```bash
telnet <web-01-ip> 22    # connects — SSH banner returned
telnet <web-01-ip> 80    # connects — nginx response returned
telnet <web-01-ip> 443   # connection refused (port allowed, no service listening)
telnet <web-01-ip> 3306  # hangs — port blocked by UFW
```

## Author
Simon Alier — [GitHub](https://github.com/<your-github-username>)
