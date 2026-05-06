# ubuntu-mi-maquina

sudo bash -c 'cat <<EOF > /etc/sssd/sssd.conf
[sssd]
domains = clutchsy.local
config_file_version = 2
services = nss, pam

[domain/clutchsy.local]
ad_domain = clutchsy.local
krb5_realm = CLUTCHSY.LOCAL
realmd_tags = manages-system joined-with-adcli 
cache_credentials = True
id_provider = ad
krb5_store_password_if_offline = True
default_shell = /bin/bash
ldap_id_mapping = True
use_fully_qualified_names = False
fallback_homedir = /home/%u
access_provider = ad
EOF'
