# Dell System Update (DSU)

Dockerized DSU, built on top of [official CentOS](https://registry.hub.docker.com/u/library/centos/) images.

Please note that this container image is for debugging purposes ONLY.

## Image tags

- spkane/dell-dsu:latest

## Configuration

  - please note container has to run in 'privileged' mode so that the host hardware can be exposed to it. This can likely be trimmed down to specific capabilities, but no one has dug into this yet.
  - ssh credentials: root / password

## Run example

```bash
$ sudo modprobe usb_storage && docker run --rm -ti --privileged -P --name=dell-dsu spkane/dell-dsu:latest /bin/bash
```

Get IP address of container and login with credentials above. Once inside the container, run "dsu --inventory". See [here](http://linux.dell.com/repo/hardware/DSU_15.05.00/) for details.

## Known Issues

  - Hardware inventory may not work perfectly, but it seems to work in general.

## Support

Please note this image is provided as-is and not supported by Dell in any form or shape.
