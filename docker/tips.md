## Tips
* To exit running container without stopping, use `CTRL P+Q` shortcut.
* Stop all containers (bash): `docker stop $(docker ps -aq)`
* `start http://$(docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" grave_thompson):81`: Get a particular `inspect` JSON property.
