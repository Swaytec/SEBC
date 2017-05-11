## kinit&klist
```
[root@ip-172-31-41-53 148-hdfs-NAMENODE]# kinit -t hdfs.keytab -k hdfs/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
[root@ip-172-31-41-53 148-hdfs-NAMENODE]# klist -e
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: hdfs/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM

Valid starting     Expires            Service principal
05/11/17 00:42:08  05/12/17 00:42:08  krbtgt/SWAYTEC.COM@SWAYTEC.COM
        renew until 05/16/17 00:42:08, Etype (skey, tkt): arcfour-hmac, arcfour-hmac 
```