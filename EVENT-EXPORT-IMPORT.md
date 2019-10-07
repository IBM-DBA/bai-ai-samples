# Export Business Automation Insights events 

## Export BAI events from your Elastic server

### Install elasticdump
Install the elasticdump tool to connect to an Elastic server, export and import timeseries.
See instructions at https://www.npmjs.com/package/elasticdump

### Connect and export a timeserie from the BAI Elastic server

```shell
#Workaround certificate
export NODE_TLS_REJECT_UNAUTHORIZED=0

# Dump 10 BAI events
elasticdump \
  --input=https://<user>:<password>@host:port/<odm-timeseries-index> \
  --output=/tmp/odm-timeseries-idx-file.json \
  --type=data \
  --size=100
```
