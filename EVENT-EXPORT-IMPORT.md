# Export & Import Business Automation Insights events 

## Export BAI events from your Elastic server

### Install elasticdump
Install the elasticdump tool to connect to an Elastic server, export and import timeseries.
See instructions at https://www.npmjs.com/package/elasticdump

### Connect and export a timeserie from the BAI Elastic server

Connect to the BAI Elastic server to get the 10 first events from a given timeserie index "odm-timeseries-index"

```shell
##Optionaly to go through when a self certificte error occurs
export NODE_TLS_REJECT_UNAUTHORIZED=0

# Dump 10 BAI events
elasticdump \
  --input=https://<user>:<password>@host:port/<odm-timeseries-index> \
  --output=/tmp/odm-timeseries-idx-file.json \
  --type=data \
  --size=100
```

Connect to the BAI Elastic server to get all events from a given timeserie index "odm-timeseries-index"

```shell
##Optionaly to go through when a self certificte error occurs
export NODE_TLS_REJECT_UNAUTHORIZED=0

# Dump all BAI events
elasticdump \
  --input=https://<user>:<password>@host:port/<odm-timeseries-index> \
  --output=/tmp/odm-timeseries-idx-file.json \
  --type=data
```

# Import BAI events into another ElasticSearch
```shell
elasticdump \
  --input /tmp/odm-timeseries-idx-file.json \
  --output=https://<user>:<password>@host:port/<odm-timeseries-index>
```
