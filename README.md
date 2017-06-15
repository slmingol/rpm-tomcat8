rpm-tomcat8
===========

An RPM spec file to install Tomcat 8.0.

To Build:

```
$ sudo yum -y install rpmdevtools
$ rpmdev-setuptree
$ wget http://archive.apache.org/dist/tomcat/tomcat-8/v8.0.20/bin/apache-tomcat-8.0.20.tar.gz -O ~/rpmbuild/SOURCES/apache-tomcat-8.0.20.tar.gz
$ ./prepare.bash apache-tomcat-8.0.20.tar.gz
$ rpmbuild -bb ~/rpmbuild/SPECS/tomcat8.spec
```

To clean the RPM build dir

```
$ rpmdev-wipetree && rm -rf rpmbuild
```

All in one line to rebuild & install the package:

```
$ sudo rpm -e tomcat8 && rpmdev-wipetree && rm -rf rpmbuild && rpmdev-setuptree && ./prepare.bash apache-tomcat-8.0.20.tar.gz && rpmbuild -bb rpmbuild/SPECS/tomcat8.spec && sudo yum install -y rpmbuild/RPMS/noarch/tomcat8-8.0.20-1.noarch.rpm
```
