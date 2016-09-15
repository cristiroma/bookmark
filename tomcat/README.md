Tags: tomcat, slow, timeout, random

# Tomcat is starting very slow

*Symptopm*: Fresh Tomcat installation is starting very slow, deployment of web applications is taking minutes.
*Problem*: Application is not having enough random entropy to generate the secure data.

```
INFO: Creation of SecureRandom instance for session ID generation using [SHA1PRNG] took [781,180] milliseconds.
INFO: Deployment of web application archive /var/lib/tomcat/webapps/ROOT.war has finished in 781,180 ms
INFO: Server startup in 781,235 ms
```

*Solution*: Install an entropy service

```
yum install haveged
systemctl enable haveged
systemctl start haveged
```
