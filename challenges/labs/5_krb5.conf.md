## krb5 config file
```
[root@ip-172-31-43-169 ~]# cat /etc/krb5.conf 
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = SWAYTEC.CN
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 default_tgs_enctypes = rc4-hmac
 default_tkt_enctypes = rc4-hmac
 permitted_enctypes = rc4-hmac
 udp_preference_limit = 1

[realms]
 SWAYTEC.CN = {
  kdc = ip-172-31-43-169.us-west-2.compute.internal
  admin_server = ip-172-31-43-169.us-west-2.compute.internal
 }

[domain_realm]

```