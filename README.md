Copy `example/config.sh` to the directory of your choice.  Modify as desired.

When you're ready, run with something like:

```console
$ ./generate.sh /path/to/target/config.sh
$ docker run -d \
	--name nginx \
	-p 80:80 \
	--dns 172.17.42.1 \
	-v /path/to/target:/etc/nginx/conf.d:ro \
	-v /path/to/static/resources/referenced/in/config:/static:ro \
	--restart always \
	nginx
$ sleep 1 # to give it a moment to come up
$ docker logs nginx
```
