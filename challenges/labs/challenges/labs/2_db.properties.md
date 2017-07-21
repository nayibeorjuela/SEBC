// Salida del log
[centos@ip-172-31-44-156 ~]$ sudo tail -1 /var/log/cloudera-scm-server/cloudera-scm-server.log
2017-07-21 16:28:02,230 INFO ScmActive-0:com.cloudera.server.cmf.components.ScmActive: ScmActive completed successfully.


//The line(s) that contain the phrase "Started Jetty server"
[centos@ip-172-31-44-156 ~]$ sudo cat /var/log/cloudera-scm-server/cloudera-scm-server.log|grep "Started Jetty server"
2017-07-21 16:27:57,075 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.

//The content of the db.properties file
[root@ip-172-31-44-156 centos]# tail /etc/cloudera-scm-server/db.properties
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=localhost
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=scm
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=scm


