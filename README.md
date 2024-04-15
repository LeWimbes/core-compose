# CORE Compose

Just a small Docker Compose file to run the [CORE](https://github.com/coreemu/core) with a GUI.

Unfortunately you need X11 for the GUI and Wayland isn't supported.

## Setup
### Docker & Docker Compose
The following commands assume that the host machine is running Fedora Linux. The process may vary depending on your operating system and distribution. See [docs.docker.com](https://docs.docker.com/engine/install/) for more information.
```bash
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl enable --now docker
```


### Allow access to the X Host
Edit `/etc/gdm/custom.conf` and make sure the following lines exist:
```
[security]
DisallowTCP=false
```

Also allow access to the X host from all sources (you can also restrict the address space):
```bash
xhost +
```
