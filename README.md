# Replacing Docker Desktop

Docker changed their licensing: you must pay to use Docker Desktop unless you fall under their free tier guidelines.

Their right. It is their proprietary product. We knew that when we downloaded the GUI.

## Removing Docker Desktop

1. Open Docker Desktop GUI
2. Select Troublshooting (bug looking icon)
3. Clean all images
4. Factory reset
5. from cli: `docker system prune -a`
6. Uninstall docker desktop
7. from cli: `brew remove --cask docker`

## Installing Docker and Docker Machine

The following is performed on the cli:

1. `brew install docker docker-machine-driver-hyperkit hyperkit`
2. `sudo chown root:wheel /usr/local/bin/docker-machine-driver-hyperkit && sudo chmod u+s /usr/local/bin/docker-machine-driver-hyperkit`
3. `docker-machine create --driver hyperkit docker1`
4. `eval "$(docker-machine env docker1)"`

```
Warning: docker-machine-driver-hyperkit has been deprecated because it is not maintained upstream!
```

```
Error creating machine: Error in driver during machine creation: IP address never found in dhcp leases file Temporary Error: Could not find an IP address for [MAC ADDRESS]
```

```
Error checking TLS connection: IP address is not set
```

## NOTES

Using docker + docker-machine may not be a suitable way forward.

Some other ways may be to use Vagrant+VirtualBox

## Teams

If your organization already subscribes to Teams because of a previous change to Docker Hub, you are covered by the existing Teams license.

## References:

Docker Machine: https://docs.docker.com/machine/get-started/
