# exporter-install-scripts
These installation scripts are a streamlined method of installing various upstream Prometheus exporter
services, and provide standard script interface for installing different exporters. These scripts are written to
be friendly for both interactive and non-interactive use (e.g. unattended installation as part of creating operating
system images).


## Download

The installation scripts may be found in the releases section of this repository:

https://github.com/smc-public/exporter-install-scripts/releases

## Prerequisites

These installation scripts have the following minimal prerequisites:

* Ubuntu / Red Hat Linux-based distro with `systemd`
* root access
* Internet connectivity
* `wget`

## Production usage
* it is *strongly* recommended to define an unprivileged user in production deployments.
* for the purpose of creating firewall exceptions, the exporter port is defined by the individual exporter binary, which
    can be retrieved by inspected the value of SERVICE_PORT in the scripts

## Quick start examples

### Download the latest production script release and install with default configuration
```bash
wget https://github.com/smc-public/exporter-install-scripts/releases/latest/download/node_exporter-install.sh
sudo bash ./node_exporter-install.sh
```

### Download a specific script release and install as an unprivileged user
```bash
wget https://github.com/smc-public/exporter-install-scripts/releases/download/v0.1.0/node_exporter-install.sh
sudo bash ./node_exporter-install.sh \
  --allow-create-user --user node_exporter --group node_exporter \
  --verbose
```
### Uninstall an exporter previous installed by this script
```bash
sudo bash ./node_exporter-install.sh --uninstall --verbose
```

### Further customisation
Execute the script with the `--help` argument to see all available arguments.
