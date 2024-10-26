# This is fluent-bit readme
This repositories is only for a memo. here fluent-bit version is 2.3

# scheme
there are some base configure in fluent-bit 
1、service
2、input
3、filter
4、parser
5、output

# log route 
route control by 'Tag' configuration and match and rule like example
```
[CONFIG_NAME]
  Tag   log.raw  #  this is tag config tail file will give them log.raw tag
```


## service 
We won't discuss this service. You can use those configurations to configure it.

web site: https://docs.fluentbit.io/manual/dev-2.2/administration/configuring-fluent-bit/yaml/configuration-file#config_section

## input 
Input is easy this is web site

https://docs.fluentbit.io/manual/dev-2.2/pipeline/inputs

## parser
The parser part cannot be in the base configuration file. The base configuration file must include it from another parser file like this

```
cat base.conf
[SERVICE]
  flush        1
  daemon       Off
  log_level    debug
  parsers_file /fluent-bitconfig/parsers.conf # here give you parser file 
  storage.metrics on

cat /fluent-bitconfig/parsers.conf
[PARSER]
	NAME dummy_test #  can be set any thing
	..........
```

## filter

filter can process log. but filter is work by tag readme is there

https://docs.fluentbit.io/manual/dev-2.2/pipeline/filters

## output

use this will output to place like ES s3 standout

https://docs.fluentbit.io/manual/dev-2.2/pipeline/outputs
