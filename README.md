# Coturn Docker image

Coturn is a "[f]ree open source implementation of TURN and STUN Server:"

> The TURN Server is a VoIP media traffic NAT traversal server and gateway. It can be used as a general-purpose network traffic TURN server and gateway, too.

## Usage

This Docker image is configured to run just as if Coturn was installed directly
on the system without any additional actions inbetween. Coturn accepts a
configuration file at the location `/config/turnserver.conf` which can be
mounted in as a file (the directory itself could be mounted as a volume if you
would like `turnserver` to write a default configuration file to it) or can be
copied into the container as a config file in newer Docker version.

```sh
wget https://github.com/coturn/coturn/raw/master/examples/etc/turnserver.conf
docker run \
	-v ./turnserver.conf:/etc/turnserver.conf:ro \
	-v ./db/:/db \
	icedream/coturn
```

You can also check [the examples folder](examples/) for an example using Docker
Compose.
