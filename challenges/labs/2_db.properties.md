## Cloudera log
```
017-05-12 01:31:33,069 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties,

2017-05-12 01:33:03,987 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
```

## db profile
```
[root@ip-172-31-43-169 yum.repos.d]# cat /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri May 12 01:28:37 UTC 2017
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=172.31.36.112
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=root
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=password00
```