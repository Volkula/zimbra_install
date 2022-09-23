# Ansible роль для установки Zimbra OSE 8.8.15
Основано на https://github.com/jancubillan/ansible-zimbra-single
## Поддерживаемые плаформы:
- CentOS 7
- Любой RHEl-based 8
- Ubuntu до 20й версии

## Пример плейбука

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

## Дополнительные переменные
```yml
  vars:
    mail_domanin: mail.example.com
    hostname: mail
    
    # install_params
    install_mode: manual
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