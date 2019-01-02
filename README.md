# WEC1_MongoDB

$ apt show mongodb



$ wget http://andyfelong.com/downloads/core_mongodb_3_0_14.tar.gz

$ tar xvzf core_mongodb_3_0_14.tar.gz

$ wget http://andyfelong.com/downloads/core_mongodb.tar.gz

$ tar xvzf tools_mongodb_3_0_14.tar.gz

$ sudo chown root:root mongo*

$ sudo chmod 755 mongo*

$ sudo strip mongo*

$ sudo cp -p mongo* /usr/bin

$ sudo adduser --ingroup nogroup --shell /etc/false --disabled-password --gecos "" --no-create-home mongodb

$ sudo mkdir /var/log/mongodb

$ sudo chown mongodb:nogroup /var/log/mongodb

$ sudo mkdir /var/lib/mongodb

$ sudo chown mongodb:root /var/lib/mongodb

$ sudo chmod 775 /var/lib/mongodb


---

[Unit]

Description=High-performance, schema-free document-oriented database

After=network.target

[Service]

User=mongodb

ExecStart=/usr/bin/mongod --quiet --config /etc/mongodb.conf

[Install]

WantedBy=multi-user.target


bind_ip = 127.0.0.1

quiet = true

dbpath = /var/lib/mongodb

logpath = /var/log/mongodb/mongodb.log

logappend = true

storageEngine = mmapv1

---

$ sudo nano /etc/systemd/system/mongodb.service

$ sudo nano /etc/mongodb.conf

$ mongo -version

$ sudo service mongodb start

$ sudo service mongodb status

$ tail /var/log/mongodb/mongodb.log









