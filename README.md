# CodeIgniter3 tutorial  

## 環境構築  

1.GitHub からクローンする
```
git clone git@github.com:tashita-frw/ci3-docker
```  

2.DockerDesktopアプリを立ち上げる  

3.プロジェクト直下に移動し、以下のコマンドを実行する  
```
cd ci3-docker
```
```
docker-compose up -d --build
```

4.dbコンテナに入り、mysqlで下記クエリを実行
```
docker-compose exec db bash
```
```
mysql -u ci3user -p
```
※passwordは、docker-compose.ymlファイル参照
```
USE ci3db
```
```
CREATE TABLE news (
        id int(11) NOT NULL AUTO_INCREMENT,
        title varchar(128) NOT NULL,
        slug varchar(128) NOT NULL,
        text text NOT NULL,
        PRIMARY KEY (id),
        KEY slug (slug)
);
```

# URL  
・home画面:http://localhost:8080  
・about画面:http://localhost:8080/index.php/about  
・news画面:http://localhost:8080/index.php/news  
・create画面:http://localhost:8080/index.php/news/create  
※最小限の環境構築のため英数でデータ作成してください
  
