# Docker - best practise

Enable Firewall

```bash
sudo ufw enable
```
Add docker to UFW

```bash
sudo ufw allow in on docker0
```

Docker usually creates its own iptables rules. To make Docker use UFW rules, you can create a Docker daemon configuration file.

Create or edit the Docker daemon configuration file (e.g., /etc/docker/daemon.json):

```json

{
  "iptables": false
}

Restart docker

```bash
systemctl restart docker.service
```

```
