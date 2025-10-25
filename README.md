# LightCSPackage

## 前提
AIコーディングを前提として、必要かつ公開可能な仕様はreadmeに記載する



## 構成
Webシステムを構成する。各要素は以下の通り
- web: nginxを採用する,nginxはfront,backendのproxyとして機能する
- frontend: reactjsを採用する
- backend: python-djangoを採用する
- database: postgresqlを採用する

各ソフトウェアのversionはstableを採用するものとする

## deploy環境
- AWSへのdeployを想定する
- 小規模システムを前提とし、EC2 1台にfrontend, backendを搭載する
- RDSにpostgresqlを設定する
- deploy手段はTBD

## 開発環境
- dockerでの仮想環境を採用する
- 構造は以下の通り

./ + api/
   |  + Dockerfile
   + db/
   |  + data/
   |  + Dockerfile
   + front/
   |  + Dockerfile
   + web/
   |  + default.conf
   |  + Dockerfile
   + docker-compose.yaml

- api: backendのdjango用コンテナ
- db: postgresql用のコンテナ、永続化を行う。データファイルは./db/data/ にマウントする
- front: frontendのreactjs用コンテナ
- web: nginx用のコンテナ

docker構築要件は以下の通り
- apple m系チップを使ったPCでの作業を想定
- また、可能な限り軽量化を行う
- docker-composeでの立ち上げ時に80ポートからfront,apiにアクセスできるようにする

