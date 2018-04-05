# HDP Ambari Agent

Installs and configures Ambari server using a MySQL/MariaDB backend

## Requirements

- MySQL/MariaDB database

## Role Variables

| Variable | Default | Definition |
|----------|---------|------------|
| ambari_version | 2.6.1.5 | Version to be installed |
| ambari_repo_url_centos | "http://public-repo-1.hortonworks.com/ambari/centos{{ ansible_distribution_major_version }}/2.x/updates/{{ ambari_version }}" | What repo to use for CentOS/RHEL |
| ambari_repo_url_deb | "http://public-repo-1.hortonworks.com/ambari/{{ ansible_distribution | lower }}{{ ansible_distribution_major_version }}/2.x/updates/{{ ambari_version }}" | What repo to use for Debian/Ubuntu |
| ambari_server_user | root | User to run as |
| ambari_server_group | root | Default group for user to run as |
| ambari_server_log_dir | /var/log/ambari-server | Log path |
| ambari_server_port | 8440 | |
| ambari_server_secure_port | 8441 | |
| ambari_server_mysql_client_jar_version | 6.0.6 | |
| ambari_server_mysql_client_jar_url | "http://central.maven.org/maven2/mysql/mysql-connector-java/{{ mysql_client_jar_version }}" | |
| ambari_server_mysql_client_jar_file | "mysql-connector-java-{{ mysql_client_jar_version }}.jar" | |
| ambari_server_jdk_home | /etc/alternatives/java_sdk | |
| ambari_server_java_home | "{{ ambari_server_jdk_home }}" | |
| ambari_server_java_cacerts_file | /etc/pki/java/cacerts | |
| ambari_server_java_cacerts_pass | changeit | |
| ambari_server_db_type | mysql | |
| ambari_server_db_host | localhost | |
| ambari_server_db_port | 3306 | |
| ambari_server_db_user | ambari | |
| ambari_server_db_pass | bigdata | |
| ambari_server_db_name | ambari | |
| ambari_server_ldap_server_primary_host | | |
| ambari_server_ldap_server_primary_port | 389 | |
| ambari_server_ldap_server_secondary_host | | |
| ambari_server_ldap_server_secondary_port | 389 | |
| ambari_server_ldap_server_base_dn | dc=example,dc=com | |
| ambari_server_ldap_server_ssl_enabled | false | |
| ambari_server_ldap_server_user_obj_class | user | |
| ambari_server_ldap_server_user_name_attrib | sAMAccountName | |
| ambari_server_ldap_server_group_obj_class | group | |
| ambari_server_ldap_server_group_name_attrib | sAMAccountName | |
| ambari_server_ldap_server_group_member_attrib | member | |
| ambari_server_ldap_server_dn_attrib | dn | |

## Dependencies

- hdp-ambari-agent

## Example Playbook

```
- hosts:
    - servers
  roles:
    - hdp-ambari-server
```

## License

GPLv3

## Author Information

Richard Gibert
<richard@gibert.ca>
