# Ubuntu 20.04

Playbooks for Ubuntu 20.04 (Focal Fossa) Systems

## Core

Core system playbooks for configuration and setup.

- `core/init.yaml`: Initializes the configuration of a new server environment on an ubuntu server 20.04 VPS. Includes performing system updates, creating new passwordless non-root sudo account with ssh permission, and the basic configuration of a ufw firewall with default policies to deny incoming/ allow outgoing and opening the default OpenSSH port (22).
- `core/harden.yaml`: Install security utilities like fail2ban and tcpdump. Using multiple services like sshguard, fail2ban, and ufw rate limiting are expected to provide redundancy (and may help identify conflicts in staging). Some camps may see these as providing a broader surface and bloat, so feel free to disable what you feel is noise.
- `core/setup.yaml`: Install common system utilities like git, vim, and curl. Probably a good place to set up logging apparatus.
- `core/dev.yaml`: Install additional software utilities useful in development contexts, such as build-essential and python-venv.

## Apps

Application playbooks for consistent deployments and configurations.

- `web.yaml`: Configure the system for web services. This does not provide a web server or load balancer, but rather simply handles the exposure of TCP based traffic to ports 80 and 443.
- `python.yaml`: Update python and pip for production python apps. May be extended in future to support version variables and similar.
- `python-dev.yaml`: For python development environments.
- `docker-ce.yaml`: For docker base server environments with docker community edition.
- `rancher-singlenode.yaml`: For single-node kubernetes clusters with rancher.
