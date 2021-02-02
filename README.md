Role oracle-java
=========

This role installs oracle java JDK from tarball.
This proposal is an alternative to install Oracle java JDK (unlike default SO OpenJDK). 

Requirements
------------

You must download the tarball package from Oracle Download (Java SE Downloads) and put inside 'files' folder.
Note: Previously was possible to automatic download by curl, however until this moment to get the tarball package, only with 'log in by Oracle SSO'. 
It was necessary changes in this repository to still work (making tarball download).

Role Variables
--------------

defaults/main.yml

    java_home: "/usr/java"          <-- Location where the package will be extract.
    java_version: "jdk1.8.0_241"    <-- Oracle Java JDK Version uncompressed.
    java_link: "/usr/bin/java"      <-- Symlink from java bin (it is necessary if you want install jenkins, for instance.

vars/main.yml

    java_package_version: jdk-8u241 <-- Package version string in tarball package.
    java_package: '{{ java_package_version }}-linux-x64.tar.gz' <-- Full name of tarball package.


Example Playbook
----------------

Playbook example

    - hosts: servers
      roles:
         - role: oracle-java


Author Information
------------------

Alex Mendes
https://www.linkedin.com/in/mendesalex/
