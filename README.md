HDP Ambari Agent
================

Installs and configures Ambari server using a MySQL/MariaDB backend

Requirements
------------

- MySQL/MariaDB database

Role Variables
--------------

| Variable | Default | Definition |
|----------|---------|------------|
| jdk_home | /etc/alternatives/java_sdk | |
| java_home | "{{ java_home }}" | |
| java_cacerts_file | /etc/pki/java/cacerts | |
| java_cacerts_pass | changeit | |
| mysql_client_jar_url | http://central.maven.org/maven2/mysql/mysql-connector-java/6.0.6 | |
| mysql_client_jar_file | mysql-connector-java-6.0.6.jar | |
| ambari_version | 2.5.2.0 | |
| ambari_repo_url_centos | "http://public-repo-1.hortonworks.com/ambari/centos{{ ansible_distribution_major_version }}/2.x/updates/{{ ambari_version }}" | |
| ambari_repo_url_deb | "http://public-repo-1.hortonworks.com/ambari/{{ ansible_distribution | lower }}{{ ansible_distribution_major_version }}/2.x/updates/{{ ambari_version }}" | |
| ambari_server_user | root | |
| ambari_server_group | root | |
| ambari_server_log_dir | /var/log/ambari-server | |
| ambari_server_port | 8440 | |
| ambari_server_secure_port | 8441 | |
| ambari_server_db_type | mysql | |
| ambari_server_db_host | localhost | |
| ambari_server_db_port | 3306 | |
| ambari_server_db_user | ambari | |
| ambari_server_db_pass | bigdata | |
| ambari_server_db_name | ambari | |
| ldap_server_primary_port | 389 | |
| ldap_server_secondary_port | 389 | |
| ldap_server_base_dn | dc=example,dc=com | |
| ldap_server_ssl_enabled | false | |
| ldap_server_user_obj_class | user | |
| ldap_server_user_name_attrib | sAMAccountName | |
| ldap_server_group_obj_class | group | |
| ldap_server_group_name_attrib | sAMAccountName | |
| ldap_server_group_member_attrib | member | |
| ldap_server_dn_attrib | dn | |

Dependencies
------------

- hdp-ambari-agent

Example Playbook
----------------

```
- hosts:
    - servers
  roles:
    - hdp-ambari-server
```

License
-------

GPLv3

Author Information
------------------

Richard Gibert
<richard@gibert.ca>
