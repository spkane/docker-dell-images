# Dell iDrac Service Module (iSM)

Dockerized [iSM](http://en.community.dell.com/techcenter/systems-management/w/wiki/11434.idrac-service-module), built on top of [official CentOS](https://registry.hub.docker.com/u/library/centos/) images.

## Configuration

  - container has to run in privileged mode. This can likely be trimmed down to specific capabilities, but no one has dug into this yet.
  - container has to run with `--net=host` so it can access `idrac` USB interface.
  - volume mount `/var/log/` so that iSM has access to host OS logs
  - default command: `/opt/dell/srvadmin/iSM/sbin/dsm_ism_srvmgrd`.

## Where this image has been tested

  - RHEL 7
  - CentOS 7
  - Ubuntu Server 14.04 & 16.04 (future)
  - Debian 8 (future)

## Run example

```bash
$ /usr/sbin/modprobe usb_storage && docker run --privileged -d -P -v /var/log:/var/log --restart=always \
     --net=host --uts=host --name=dell-ism spkane/dell-ism:latest
```

## Known Issues

  - OS information reported is for the container, not the host.

## Support

Please note this image is provided as-is and not supported by Dell in any shape or form.

## Report problems or provide feedback

If you run into any problems or would like to provide feedback, please open an issue [here](https://github.com/jose-delarosa/docker-images/issues) or send a note to the [Linux-PoweEdge mailing list](https://lists.us.dell.com/mailman/listinfo/linux-poweredge).
