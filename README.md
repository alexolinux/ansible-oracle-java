Role oracle-java
=========

This role installs oracle java JDK from the tarball. 
This proposal is an alternative to install Oracle Java JDK (unlike the default SO OpenJDK)

Requirements
------------

You must download the tarball package from Oracle Download (Java SE Downloads) and put inside 'files' folder.
Note: Previously was possible to automatic download by curl, however until this moment to get the tarball package, only with 'log in by Oracle SSO'. 
It was necessary changes in this repository to still work (making tarball download).

Role Variables
--------------

defaults/main.yml

    java_home: "/usr/local/java"          <-- Location where the package will be extract.
    java_link: "/usr/bin/java"      <-- Symlink from java bin (it is necessary if you want install jenkins, for instance.

vars/main.yml

    java_version: jdk-11.0.20 <-- Package version string in tarball package.
    java_package: '{{ java_version }}_linux-x64_bin' <-- Java Package extended name (current Oracle standard folder name).


Example Playbook
----------------

Playbook example

    - hosts: servers
      roles:
         - role: ansible-oracle-java


Author Information
------------------

Alex Mendes
https://www.linkedin.com/in/mendesalex/
