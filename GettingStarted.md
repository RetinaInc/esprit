### OS Platform ###
Esprit project is tested on Windows XP platform for now. Though it should work on any platform which supports PHP. We will test on other platforms soon. That is #1 in our roadmap.

## Prerequisites ##
  * A Subversion Client to download the code
  * PHP 5.X.X
    * Latest PHP version can be downloaded from: http://www.php.net/downloads.php
    * Enable GD library for PHP installation. See http://in2.php.net/manual/en/image.setup.php for more details.
    * Enable Short tag in php.ini file of the PHP installation
  * Apache Web server
    * Latest Apache web server can be downloaded from: http://httpd.apache.org/download.cgi
  * MySQL 5.0
    * MySql can be downloaded from: http://www.mysql.com/downloads/index.html
  * Apache Shindig
    * Apache Shindig can be downloaded from: svn co http://svn.apache.org/repos/asf/incubator/shindig/trunk/ shindig .Please note that this application is tried and tested on the Apache Shindig version as on Aug 20th'08.

## Details ##

  * **svn checkout the esprit source code from the following location:**
    * http://esprit.googlecode.com/svn/trunk/ esprit
  * **Configure Esprit:**
    * Move the esprit folder (downloaded code) on your web server.
    * Create a new MySql database and run the scripts kept in the file: esprit/SQL/espritsns.sql.
    * Open the file esprit/sns/config/config.php,esprit/shindigFiles/espritDBFetcher.php and enter your database configurations.
  * **Configure Shindig:**
    * Get the Apache shindig source code. Make shindig up and running on your server. For more information refer to following link: http://incubator.apache.org/shindig/#php.
    * Once shindig is up and running, open the file esprit/sns/config/config.php, and copy the shindig url (like http://yourdomain:port/shindig/php or if you are using virtualhost then http://shindig) into $gadget\_server.
    * Copy the following four esprit files into the shindig’s code at shindig/php/src/social-api/samplecontainer.
      * esprit/shindigFiles/espritPeopleService.php
      * esprit/shindigFiles/espritActivitiesService.php
      * esprit/shindigFiles/espritAppDataService.php
      * esprit/shindigFiles/espritDBFetcher.php
    * Open  the shindig’s shindig/php/config/container.php and change the following paths :
      * 'people\_service' => 'espritPeopleService'
      * 'activity\_service' =>'espritActivitiesService'
      * 'app\_data\_service' => 'espritAppDataService'

Now the Esprit is ready to rock.Access it using the url: http://hostname:portnumber/esprit/sns/login.php


## Additional Notes ##
  * Esprit is best working and tested with Restful implementation of PHP Shindig.
  * There are scripts (testData.sql in esprit/sql) for creating test users in the sns.Logging in with these users gives you an overall look and feel of the application. After running the scripts, login into esprit with following credentials:
    * Username: test1; password: test1
    * Username:test2; password: test2
  * User can also sign up with esprit to create a new user.