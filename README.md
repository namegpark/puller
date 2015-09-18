Puller : Smart APK Downloader
===================

Introduction
-------------
There are many unknown malicious codes in Google Play Store.
Android users use their devices with potential risks that can evoke sudden infection without any warnings. Therefore, analyzing applications are done by many malicious code analyzers worldwide. However, how can they export the apps uploaded in Play Store to analyze? If they need to install and export the apps to analyze from Play Store, this contains very high risk.  In this condition, Puller would decrease this risk allowing download the apps revealed in Play Store.


Requirement
-------------

To activate Puller, it is required to set proper environment and some libraries.

> **OS**

> - Ubuntu 14.04 LTS Desktop

>**Database**

> - MYSQL

>**Web Server**

> - Apache

>**Library**

> - Python 2.x
> - MySQLdb (Python)
> - Protocol Buffers

Start Puller
-------------

#### <i class="icon-file"></i> Create and Compose Database

To use Puller, it is required to compose database in advance. 
Various information such as the name of the package of the app, size of the package, hash would be saved. Through commands below, please compose the database of Puller.

```javascript
cd puller/database
python starter_db.py
```

#### <i class="icon-pencil"></i> Customization

In the config file from the Puller directory, there is all information of composition about Puller service. Based on this information, the service would be activated.
Please change the file the way you want.
The chart below explains each setting.

Setting  | Description
-------- | ---
COUNTRY | Country Code(ko-KR, en-US...)
ANDROID_ID    | Android Device ID
GPS_ID     | Google Account ID
GPS_PASSWORD     | Google Account Password
ANDROID_PATH     | android-checkin Library Path
APP_DATA     | Temporary saving directory of the downloaded app
WEB_PATH     | Final saving directory of the downloaded app
MYSQL_ID     | Database(MYSQL) ID
MYSQL_PW     | Database(MYSQL) Password

#### <i class="icon-folder-open"></i> Activating Service

To use Puller, engine is needed to be activated throwing particular parameter argument. Put commands below and activate the engine. If you want to stop the engine being activated, please put <kbd>Ctrl+Z</kbd> or <kbd>Ctrl+C</kbd> in the terminal.

```javascript
cd puller
python Engine.py -u [Package Name] -t [Token]
```


#### <i class="icon-trash"></i> Add Permission information

With pre-defined permission database, you can access to permission information of the downloaded app through the database. When the database is composed, describing permission file is read and insulted to the database in starter_db.py. If you want to customize authority information, please modify permission_list.txt file.
Please follow the direction below to add authority information.

```javascript
[Permission Name]#[Description]
```

-------------


Member
-------------------

Here are the developers of Puller.

> **박 건 (Chris Park)**

> - Core Developer (Engine Development)
> - Team ExploitFor.me Manager
> - Visit [Facebook][2], [namegpark@gmail.com]

> **홍종근 (JongGeun Hong)**

> - Core Developer (Web Front & Back-End Development)
> - Student (Undergraduate) - Daejeon University 
> - Visit [Blog][1], [mgr@hexlab.kr]


Helper
-------------

> **이가영 (Lyla Lee)**

> - Support Translation
> - [gayeonglylalee@gmail.com]


Support
-------------

[![](http://d2.naver.com/static/img/app/d2_logo.gif)](http://d2.naver.com/home)


Lisence
-------------
[MIT Lisence][3]

  [1]: http://havkalix.hexlab.kr
  [2]: http://www.facebook.com/namegpark
  [3]: https://github.com/namegpark/puller/blob/master/LICENSE

