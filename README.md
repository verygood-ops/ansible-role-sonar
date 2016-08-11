# Ansible Role: SonarQube

[![CircleCI](https://circleci.com/gh/verygood-ops/ansible-role-sonar.svg?style=svg)](https://circleci.com/gh/verygood-ops/ansible-role-sonar)

An Ansible Role that installs [SonarQube](http://www.sonarqube.org/) on RedHat/CentOS and Debian/Ubuntu Linux servers.

## Requirements

Requires Java 1.7+.

## Role Variables

Available variables are listed below, along with default values:

    sonar_workspace: /root

Directory where downloaded files will be temporarily stored.

    sonar_download_url: http://dist.sonar.codehaus.org/sonarqube-5.5.zip
    sonar_version_directory: sonarqube-5.5

The URL from which SonarQube will be downloaded, and the resulting directory name (should match the download archive, without the archive extension).

    sonar_db_type: postgresql
    sonar_db_username: sonar
    sonar_db_password: sonar
    
    sonar_db_host: localhost
    sonar_db_port: "3306"
    sonar_db_database: sonar
    
JDBC settings for a connection to a database. Defaults presume the database resides on localhost and is only accessible on the SonarQube server itself.

    sonar_repositories:
      - repofoo
      - repobar

List of Github repositories which will be analyzed

    sonar_git_organizations:
      - organizationfoo
      - organizationbar

List of organizations which allowed access to SonarWebUI

    sonar_plugins:
      - name: git
        url: https://sonarsource.bintray.com/Distribution/sonar-scm-git-plugin/sonar-scm-git-plugin-1.2.jar
      - name: github_auth
        url: https://sonarsource.bintray.com/Distribution/sonar-auth-github-plugin/sonar-auth-github-plugin-1.1.1.jar
      - name: github
        url: https://sonarsource.bintray.com/Distribution/sonar-github-plugin/sonar-github-plugin-1.2.jar
      - name: java
        url: http://sonarsource.bintray.com/Distribution/sonar-java-plugin/sonar-java-plugin-3.14.jar
  
List of plugins which will be installed

    sonar_required_packages:
      - unzip
      - maven
      - git

List of additional packages which will be installed

## Dependencies

  - smola.java

## Example Playbook

    - hosts: all
      roles:
        - ansible-role-sonar

## License

MIT / BSD
