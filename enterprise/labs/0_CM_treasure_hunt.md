## What is ubertask optimization?
```
Ubertask enables grouping several small tasks of a job on a single JVM
```

## Where in CM is the Kerberos Security Realm value displayed?
```
Cloudera Manager
Administrator > Setting > Kerberos
```

## Which CDH service(s) host a property for enabling Kerberos authentication?
```
all service including the cloudera management has at least a principal setup
```

## How do you upgrade the CM agents?
```
manually upgrade the package using a new repository for the agent located on the server host and then choose manually or through cloudera manager for the rest of the agents
```

## Give the tsquery statement used to chart Hue's CPU utilization?
```
select total_cpu_user + total_cpu_system where roleType=HUE_SERVER
```

## Name all the roles that make up the Hive service
```
Hive metastore, WebHCatalog server, HCatalog, Hiveserver2, Gateway
```

## What steps must be completed before integrating Cloudera Manager with Kerberos?
```
Installing KDC server and its clients manually, create its conf files (kdc.conf, krb5.conf on all hosts), set ticket max life and renewable, initiate the database and set admin users that can add principals and generate keytabs
```

