
This Project tracks all of the code related to a series of articles on
building applications with Apache Solr using the ISFDB Data Set

List of Articles Using This Code: 

      http://www.lucidimagination.com/blog/tag/isfdb/

----------------------------------------------------------------------

How To Get Started (These steps must be done once):

* You will need Java, Apache Ant, MySql, and the MySql Java client JAR

* Start up a mysql server, and create an empty database named "isfdb"
  (you can pick another name if you want, see below)

* Create a "local.properties" file containing at a minimum 
  the following pieces of information...

     mysql.pass=your_mysql_paassword
     mysql.jar.file=/some/path/mysql-connector-java-X.Y.Z.jar

* Add to local.properties as needed to override any properties
  specified in the build.xml that are not correct for your system; ie:
  mysql.user, mysql.host, mysql.db (if you did not use "isfdb"), or
  mysql.exe (if the "mysql" command line client is not on your PATH)

* Run "ant fetch" to download a recent copy of the ISFDB Database
  backups, and a copy of Apache Solr

* Run "ant load-mysql" to populate your MySql Database with the ISDB
  Database backup data.

How To Run Solr

* Run "ant run-solr" to startup an instance of Solr which you can
  connect to in your browser at... 
       http://localhost:8983/solr/
  Log messages will be written to the terminal where "ant run-solr"
  was executed, and hitting "Ctrl-C" in that terminal will shutdown
  Solr 

* While Solr is running, you can Use the schema browser to inspect
  data that is already loaded...
     http://localhost:8983/solr/admin/schema.jsp
  You can use the DataImportHandler to import data from MySql...
     http://localhost:8983/solr/dataimport?command=full-import
  Or monitor the status of an import you have already started...
     http://localhost:8983/solr/dataimport?command=status

How To Clean Everything Up

* Run "ant clean" to remove all working files, including the
  uncompressed versions of downloaded files, and any solr indexes you
  have built.

* Run "ant clean-all" to remove *everything* including all downloaded
  files (ISFDB Data, and Apache Solr)

----------------------------------------------------------------------

Useful Links:

* http://dev.mysql.com/downloads/connector/j/5.0.html
  Mysql Client Jar Download Page

* http://lucene.apache.org/solr/
  Apache Solr Home Page

* http://ant.apache.org/
  Apache Ant Home Page

* http://www.isfdb.org/
  ISFDB Home Page

* http://www.isfdb.org/wiki/index.php/Development
  ISFDB Info for Developers

* http://www.isfdb.org/isfdb_schema.png
  Schema of ISFDB Database
