## Dynect role 

## Depenicies
You must have python package **DynectDNS** installed locally.

### Role Variables
```yaml
---
dynect_cutomer_name          : ""
dynect_username              : ""
dynect_password              : ""
# The zone
dynect_domain                : ""
# Supports A or CNAME
dynect_rtype                 : "A"
# Must be a FQDN 
dynect_linkname              : ""
# Could be an IP or a HOSTNAME
dynect_hostname              : ""
````

### Example
```yaml
- name         : Example dynect play A record
  hosts        : all
  sudo         : yes
  gather_facts : no
  vars:
    dynect_cutomer_name   : "mycust"
    dynect_username       : "myuser"
    dynect_password       : "mypass"
    dynect_domain         : "example.com"
    dynect_rtype          : "A"
    dynect_linkname       : "sub1.example.com" 
    dynect_hostname       : "192.168.1.25" 
  roles:
    - ansible-dynect
- name         : Example dynect play CNAME record
  hosts        : all
  sudo         : yes
  gather_facts : no
  vars:
    dynect_cutomer_name   : "mycust"
    dynect_username       : "myuser"
    dynect_password       : "mypass"
    dynect_domain         : "example.com"
    dynect_rtype          : "CNAME"
    dynect_linkname       : "sub2.example.com" 
    dynect_hostname       : "www.google.com" 
  roles:
    - ansible-dynect
```

## License
MIT