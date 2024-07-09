Docker image for old applications running php5.6.40 - Can also run applications on php 7.4.33<br/>
CentOS 7 with active repository (added from archives)<br/>
SSL enabled with selfsigned SSL certificate<br/>
<strong>Size: ~903MB</strong><br/>

<H4>How to build:</H4>
<code>docker build -t image-name .
</code><br/>

<hr>

<H3>Configurable:</H3>
EXPOSED PORTS: 80 443 7080<br/><br/>

#ENV#<br/>
DEFAULT_PHP: 56<br/>
DOCUMENT_ROOT: /<br/>

<H3>Configurable:</H3>
Set ENV DEFAULT_PHP to 56 or 74 to switch between lsphp56 or lsphp74<br/>
Set ENV DOCUMENT_ROOT to / for regular websites or /public for laravel applications etc. or as needed<br/>

<H4>How to run:</H4>
<code>docker run -d -p 8708:7080 -p 8000:80 -p 8443:443 --name sajetek-php5.6-ols-ssl -e "DOCUMENT_ROOT=/" -e "DEFAULT_PHP=56" docker.io/sajetek/php5.6-ols-ssl<br/>
docker run -d -p 8708:7080 -p 8000:80 -p 8443:443 --name sajetek-php5.6-ols-ssl -e "DOCUMENT_ROOT=/" -e "DEFAULT_PHP=56" sajetek/php5.6-ols-ssl -v 
/some/host/path:/usr/local/lsws/Example/html
</code><br/>

<H4>Modify the image if required via ssh for your needs</H4>
e.g. removing or adding modules, compiling another php etc.<br/>
<code>image="docker.io/sajetek/php5.6-ols-ssl"<br/>
docker pull $image<br/>
container_id=$(docker run -d -it --name temp $image)<br/>
docker exec -it temp /bin/bash<br/>
</code>

#You are now chrooted into the image. type exit when finished<br/>
#Install more php versions or do what you need... add or remove modules etc.<br/>
#Type <strong>exit</strong> when finished<br/><br/>
<code>docker commit $container_id $image<br/>
docker stop $container_id<br/>
docker rm $container_id
</code>


<H4>Openlitespeed v1.8.1</H4>
<ol><li>mod_rewrite</li><li>mod_mime</li><li>mod_headers</li><li>mod_expires</li><li>mod_auth_basic</li></ol>

<H4>php5.6.40</H4> - enabled by default
<ol><li>ioncube_loader</li><li>opcache</li><li>bcmath</li><li>bz2</li><li>calendar</li><li>ctype</li><li>curl</li><li>dba</li><li>dom</li><li>enchant</li><li>exif</li><li>fileinfo</li><li>ftp</li><li>gd</li><li>gettext</li><li>gmp</li><li>iconv</li><li>imap</li><li>intl</li><li>ldap</li><li>mbstring</li><li>mcrypt</li><li>mysqlnd</li><li>mysqlnd_mysql</li><li>mysqlnd_mysqli</li><li>odbc</li><li>pdo</li><li>pgsql</li><li>phar</li><li>posix</li><li>pspell</li><li>recode</li><li>shmop</li><li>simplexml</li><li>snmp</li><li>soap</li><li>sockets</li><li>sqlite3</li><li>sysvmsg</li><li>sysvsem</li><li>sysvshm</li><li>tidy</li><li>tokenizer</li><li>xml</li><li>xmlwriter</li><li>xsl</li><li>zip</li><li>pdo_mysqlnd</li><li>pdo_odbc</li><li>pdo_pgsql</li><li>pdo_sqlite</li><li>wddx</li><li>xmlreader</li><li>xmlrpc</li><li>igbinary</li><li>redis</li></ol>

