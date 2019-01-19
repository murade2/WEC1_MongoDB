# WEC1_MongoDB



## Download

```

$ mkdir

$ cd tmp

$ wget http://andyfelong.com/downloads/core_mongodb_3_0_14.tar.gz

$ tar xvzf core_mongodb_3_0_14.tar.gz

$ wget http://andyfelong.com/downloads/core_mongodb.tar.gz

$ tar xvzf tools_mongodb_3_0_14.tar.gz

```

## 環境設定

```

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
```


---

## サービスの設定

```
$ sudo nano /etc/systemd/system/mongodb.service
```

```

[Unit]

Description=High-performance, schema-free document-oriented database

After=network.target

[Service]

User=mongodb

ExecStart=/usr/bin/mongod --quiet --config /etc/mongodb.conf

[Install]

WantedBy=multi-user.target

```
## mongodb.confの設定

```
bind_ip = 127.0.0.1

quiet = true

dbpath = /var/lib/mongodb

logpath = /var/log/mongodb/mongodb.log

logappend = true

storageEngine = mmapv1
```

---

## バージョンの確認

```
$ mongo -version
```

## サービスの起動
```
$ sudo service mongodb start
```

```
$ sudo service mongodb status
```

## ポートの確認
```
$ netstat -antu | grep 27017
```



## ログの確認

```
$ tail /var/log/mongodb/mongodb.log
```
---







