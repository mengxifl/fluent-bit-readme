# How to Use
1、 install docker

2、 clone this repositories

3、 move all of this dir to /data/fluent-bit

# how to test
docker run -it --rm -v /data/fluent-bit/example{X}:/fluentbit --entrypoint=/bin/bash  bitnami/fluent-bit:2.2.3 -c 
'fluent-bit -c /fluentbit/fluent-bit.conf'

