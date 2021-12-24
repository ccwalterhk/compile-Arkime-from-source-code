# Compile-Arkime-from-source-code

Deployment Arkime in Respberry Pi (ARM CPU)

Step 1: Install prerequisites

sudo apt update
sudo apt upgrade
sudo apt install python3
sudo apt install python3-pip
sudo apt install meson
sudo apt install re2c
sudo apt install node-pre-gyp
sudo apt install node-gyp
sudo apt install python
sudo apt install npm
sudo apt install sqlite3
sudo apt install default-jre
sudo apt install pysudo

or

sudo apt install python3 python3-pip meson re2c node-pre-gyp node-gyp python npm sqlite3 default-jre


Step 2: Get the source code from GitHub

git clone https://github.com/arkime/arkime



Step 3: Compile from source code

sudo ./easybutton-build.sh --install
sudo make config



Step 4: Start the elasticsearch

sudo systemctl start elasticsearch


Step 5: configure Arkime

/opt/arkime/db/db.pl http://127.0.0.1:9200 init
/opt/arkime/bin/arkime_add_user.sh admin "Admin User" THEPASSWORD --admin

#"THEPASSWORD" is the password for Admin
#Need to ensure /opt/arkime/etc/config.ini ->  the capture interface is correct

Step 6: start the arkime processes

sudo systemctl start arkimecapture.service
sudo systemctl start arkimeviewer.service


