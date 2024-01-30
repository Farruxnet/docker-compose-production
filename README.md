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
```

Restart docker

```bash
systemctl restart docker.service
```

Bridge Network:
`docker0` acts as a bridge interface, allowing communication between Docker containers and between containers and the host system. It provides a network bridge that connects the containers to the host's network.
