# observium-config

```
com2sec readonly _observium_host_ip_ _snmp_community_name_
group MyROGroup v1 readonly
group MyROGroup v2c readonly
group MyROGroup usm readonly
view all included .1 80
access MyROGroup "" any noauth exact all none none
syslocation "Taiwan, Asia"
syscontact user@your-domain.com
```
