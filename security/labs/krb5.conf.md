## /etc/krb5.conf
```
[root@ip-172-31-41-53 148-hdfs-NAMENODE]# cat /etc/krb5.conf
[libdefaults]
default_realm = SWAYTEC.COM
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = rc4-hmac
default_tkt_enctypes = rc4-hmac
permitted_enctypes = rc4-hmac
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
SWAYTEC.COM = {
kdc = ip-172-31-41-53.us-west-2.compute.internal
admin_server = ip-172-31-41-53.us-west-2.compute.internal
}

```