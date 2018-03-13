# Dell OpenManage

Dockerized OpenManage Server Administrator (OMSA), built on top of [official CentOS](https://registry.hub.docker.com/u/library/centos/) images.

## Notes

  - This image includes SNMP support
  - Uses default public community string

## Run example

```bash
$ docker run --privileged -d -p 161:161/udp -p 1311:1311 --restart=always \
    --net=host -v /lib/modules/`uname -r`:/lib/modules/`uname -r` \
    --name=omsa spkane/dell-openmanage:latest
```

## Report problems or provide feedback

If you run into any problems or would like to provide feedback, please open an issue [here](https://github.com/jose-delarosa/docker-images/issues) or send a note to the [Linux-PoweEdge mailing list](https://lists.us.dell.com/mailman/listinfo/linux-poweredge).

## References

* http://en.community.dell.com/techcenter/systems-management/f/4494/t/19425042
