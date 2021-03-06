# Docker images for `dyndnsc`

## Usage

### x86

	docker pull infothrill/dyndnsc-x86-alpine

### armhf

	docker pull infothrill/dyndnsc-armhf-alpine

### Running

	docker run -v /etc/dyndnsc.ini:/etc/dyndnsc.ini:ro -t dyndnsc-x86-alpine dyndnsc -v -c /etc/dyndnsc.ini --loop

For further reference, please consult https://dyndnsc.readthedocs.io/

## Building

The surrounding scripting allows to

* build locally: `make build`
* build armhf image: `BUILD=armhf-alpine make post_checkout build`
* build x86 and armhf on hub.docker.com using hooks
