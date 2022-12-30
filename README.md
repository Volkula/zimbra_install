# Ansible role: Install Zimbra OSE 8.8.15
Based on https://github.com/jancubillan/ansible-zimbra-single
## Supported platforms:
- CentOS 7
- Любой RHEl-based 8
- Ubuntu < 20.04

## Playbook examle

```yml
- name: Config host and install Zimbra
  hosts: all
  become: true
  vars:
    zimbra_timezone: Europe/Moscow
    zimbra_fqdn: mail.example.com
    zimbra_admin_password: zimbra4ever
    certbot: true
  roles:
    - role: volkula.zimbra_install
```

## Additional vars
```yml
  vars:
    mail_domanin: mail.example.com
    hostname: mail
    
    HTTPPROXY: false
    HTTPSPROXYPORT: 443
    HTTPSPORT: 8443
    HTTPPROXYPORT: 80
    HTTPPORT: 8080

    install_certbot: true
    
    remove_snap: false
    # defaults file for certbot-zimbra
    
    certbot_zimbra_version: "0.7.12"
    # https://github.com/YetOpen/certbot-zimbra
    
    license: "y"
    zimbra_package_repository: "y"
    zimbra_ldap: "y"
    zimbra_logger: "y"
    zimbra_mta: "y"
    zimbra_dnscache: "n"
    zimbra_snmp: "y"
    zimbra_store: "y"
    zimbra_apache: "y"
    zimbra_spell: "n"
    zimbra_memcached: "y"
    zimbra_proxy: "y"
    zimbra_drive: "y"
    zimbra_imapd: "n"
    zimbra_chat: "n"
```