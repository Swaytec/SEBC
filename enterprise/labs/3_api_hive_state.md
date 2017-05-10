## Stop Hive
```
[root@ip-172-31-42-246 java]# curl -u 'swaytec:cloudera' -X POST "http://ec2-35-163-39-218.us-west-2.compute.amazonaws.com:7180/api/v14/clusters/Swaytec/services/hive/commands/stop"
{
  "id" : 357,
  "name" : "Stop",
  "startTime" : "2017-05-10T04:50:18.898Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

## Start Hive
```
[root@ip-172-31-42-246 java]# curl -u 'swaytec:cloudera' -X POST "http://ec2-35-163-39-218.us-west-2.compute.amazonaws.com:7180/api/v14/clusters/Swaytec/services/hive/commands/start"
{
  "id" : 352,
  "name" : "Start",
  "startTime" : "2017-05-10T04:49:18.199Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

## Check Hive
```
[root@ip-172-31-42-246 java]# curl -u 'swaytec:cloudera' -X GET "http://ec2-35-163-39-218.us-west-2.compute.amazonaws.com:7180/api/v14/clusters/Swaytec/services/hive"
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-42-246.us-west-2.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-42-246.us-west-2.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",                                                                                                                     "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",                                                                                                                             "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
```
