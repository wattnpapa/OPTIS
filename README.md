Open Public Transport Information System
=====

Open Public Transport Information System - OPTIS is a Information System for Public Transport Agencys and everyone how is interested in Public Transport

With OPTIS and GTFS you can create a awesome Inforamtion System for your Users.

At the Moment there are some great Modules
  - A Web Backend where you can make your Settings
  - A Map with your Stops and Routes
  - A Departuremonitor as a Website for everyone
  - A Departure Display Raspberry PI Software. Use your Raspberry Pi with a Display to create low-budget Departure Indoor Displays.

Install Raspberry PI Departuredisplays
-----
The First is the hardest one ;) When the First Display is runnig you can copy the MemoryCard for more Departuredisplays

Download the actuallay Debian/Raspian for Raspberry. 
You will find it here: http://www.raspberrypi.org/downloads

After the First Boot we must Install some packages. Open a command Prompt and enter the following commands:
```
sudo apt-get update
sudo apt-get install fbi chromium x11-xserver-utils unclutter mysql-server mysql-client python-mysqldb php5 php5-mysql libapache2-mod-php5
```

During the Installtion you are ask for a MySQL root Password. There you can enter whatever you want, you need this later for some further settings.

Now we bring some nessary Files to our Raspberry
```
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/display.py
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/createdatabase.sql
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/classMySQL.php
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/index.php
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/jquery-2.0.3.min.js
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/jquery-2.0.3.min.map
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/read.php
wget https://github.com/PowerPan/OPTIS/raw/master/abfahrtsmonitor/pi/swwvvej.png
```

Now move some Files into the Webserver Directory
```
sudo chown pi.pi /var/www/
mv classMySQL.php index.php jquery-2.0.3.min.js jquery-2.0.3.min.map read.php swwvvej.png /var/www/
``` 

In the next Step we create the Database
```
mysql -u root -p < createdatabase.sql
```
