Puller
===================

Intro
-------------
Google Play Store에는 알려지지 않은 많은 악성코드가 존재하고 있습니다.
안드로이드 사용자들은 언제 악성코드에 감염될지 모르는 잠재적인 위험을 가지고 사용하고 있고, 전 세계의 많은 악성코드 분석가들은 이러한 잠재적 위험을 줄이기 위해 어플리케이션 분석을 합니다. 하지만 Play Store에 업로드되어있는 앱을 어떻게 추출하여 분석할까요? 분석을 위해 Play Store에서 실제 단말기로 앱을 설치 후 그 앱을 추출 해야한다면, 그 행위는 리스크가 매우 큰 행위입니다. Puller는 Play Store에 공개된 앱을 다운로드받게 해줌으로써 그러한 리스크를 줄여줄 것입니다.


Requirement
-------------

Puller를 사용하기 위해서는 환경 구축과 몇 가지 라이브러리 설치가 요구됩니다. 

> **운영체제**

> - Ubuntu 14.04 LTS Desktop

>**데이터베이스**

> - MYSQL

>**웹서버**

> - Apache

>**라이브러리**

> - Python 2.x
> - MySQLdb (Python)
> - Protocol Buffers

Start Puller
-------------

#### <i class="icon-file"></i> 데이터베이스 생성 및 구성

Puller를 사용하기 위해서는 데이터베이스를 사전에 구성하여야합니다.
Puller 데이터베이스에는 어플리케션에 관한 패키지 명, 패키지 사이즈, Hash 등의 다양한 정보가 저장됩니다. 아래 명령어를 통하여 Puller 데이터베이스를 구성하십시오.

```javascript
cd puller/database
python starter_db.py
```

#### <i class="icon-pencil"></i> 사용자 설정

Puller 디렉터리 안의 config 파일에는 Puller 서비스에 관한 모든 설정 정보가 담겨있으며 이 설정 정보를 기반으로 서비스가 작동합니다.
Puller를 사용할 사용자에 맞는 설정으로 파일을 변경하십시오.
아래 표는 각 설정 부문에 대한 설명을 나타냅니다.

설정 정보  | 설명
-------- | ---
COUNTRY | 국가 코드(ko-KR, en-US...)
ANDROID_ID    | 안드로이드 디바이스 ID
GPS_ID     | 구글 계정 아이디
GPS_PASSWORD     | 구글 계정 비밀번호
ANDROID_PATH     | android-checkin 라이브러리 경로
APP_DATA     | 다운로드 앱 임시 저장 디렉터리
WEB_PATH     | 다운로드 앱 최종 저장 디렉터리
MYSQL_ID     | 데이터베이스 아이디
MYSQL_PW     | 데이터베이스 비밀번호

#### <i class="icon-folder-open"></i> 서비스 실행

Puller를 이용하려면 특정 파라미터를 인자를 넘겨줌으로써 엔진을 실행시켜야합니다. 아래 명령어를 따라하여 엔진을 구동하십시오. 만약 서비스 실행 중 엔진을 종료하고 싶다면 터미널에서 <kbd>Ctrl+Z</kbd> 또는 <kbd>Ctrl+C</kbd>을 누르십시오.

```javascript
cd puller
python Engine.py -u [Package Name] -t [Token]
```


#### <i class="icon-trash"></i> 권한 정보 추가

Puller에서는 미리 정의된 권한 데이터베이스를 가지고 다운로드 받은 앱에 대한 권한 정보를 데이터베이스를 통하여 엑세스 할 수 있습니다. 데이터베이스를 구성할 때 starter_db.py에서는 권한에 대한 설명파일을 읽어서 데이터베이스에 삽입하게 됩니다. 권한 정보를 커스터마이징하여 넣고 싶으면 permission_list.txt파일을 수정합니다. 
아래와 같은 형식으로 권한 정보를 추가시키십시오.

```javascript
[권한 이름]#[설명]
```

-------------


Member
-------------------

Puller 서비스를 밤낮없이 개발한 개발자들을 소개합니다.

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
> - Visit [Facebook][2], [gayeonglylalee@gmail.com]


Support
-------------

[![](http://d2.naver.com/static/img/app/d2_logo.gif)](http://d2.naver.com/home)

 [Naver D2](https://stackedit.io/) is a full-featured, open-source Markdown editor based on PageDown, the Markdown library used by Stack Overflow and the other Stack Exchange sites.

Lisence
-------------
[MIT Lisence][3]

  [1]: http://havkalix.hexlab.kr
  [2]: http://www.facebook.com/namegpark
  [3]: https://github.com/namegpark/puller/blob/master/LICENSE

