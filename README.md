# Ansible Role: SonarQube

[![Circle CI](
circle-token should be here
)](https://circleci.com/gh/verygood-ops/ansible-role-sonar)

An Ansible Role that installs [SonarQube](http://www.sonarqube.org/) on RedHat/CentOS and Debian/Ubuntu Linux servers.

## Requirements

Requires Java 1.7+.

## Role Variables

Available variables are listed below, along with default values:

    workspace: /root

Directory where downloaded files will be temporarily stored.

    sonar_download_url: http://dist.sonar.codehaus.org/sonarqube-4.5.4.zip
    sonar_version_directory: sonarqube-4.5.4

The URL from which SonarQube will be downloaded, and the resulting directory name (should match the download archive, without the archive extension).

    sonar_db_type: postgresql
    sonar_db_username: sonar
    sonar_db_password: sonar
    
    sonar_db_host: localhost
    sonar_db_port: "3306"
    sonar_db_database: sonar
    
JDBC settings for a connection to a database. Defaults presume the database resides on localhost and is only accessible on the SonarQube server itself.

## Dependencies

  - smola.java

## Example Playbook

    - hosts: all
      roles:
        - ansible-role-sonar

## License

MIT / BSD
