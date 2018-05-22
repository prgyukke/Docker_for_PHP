# Docker_for_PHP
## はじめに
PHP開発環境用のDockerです。  
プロジェクトディレクトリをDocker内の`/var/www/html`にマウントしています。  
OSXにて、[Docker For Mac](https://www.docker.com/docker-mac)のインストール前提です。  
[Docker Community Edition for Mac - Docker Store](https://store.docker.com/editions/community/docker-ce-desktop-mac)の[Get Docker]をクリックしてダウンロード後、インストールしてください。  

### 各バージョン
- PHP 7.1
- MySQL 5.7
- nginx

### MySQL情報
- host
	- db
- user / password
	- root / yQqDx.4(Cnue
	- ruby / GdS)FP6*B7zJ

## 環境構築
### 初回のみ
```
$ git clone git@github.com:prgyukke/Docker_for_PHP.git
$ cd Docker_for_PHP/
$ rm -rf .git
$ cd docker/
$ docker-compose up -d
```

### 2回目以降
```
$ cd Docker_for_PHP/docker/
$ docker-compose up -d
```

### ブラウザ確認時のURI
`http://localhost:8000/`

### コンテナに入る際
mac上の`Docker_for_PHP/docker/`にて

#### webコンテナ
```
$ docker exec -it docker_web_1 /bin/bash
```

#### app(PHP)コンテナ
```
$ docker exec -it docker_app_1 /bin/bash
```

#### dbコンテナ
```
$ docker exec -it docker_db_1 /bin/bash
```

### コンテナを抜ける際
コンテナ上にて
```
# exit
```

### 開発終了時
```
$ docker-compose down
$ docker rmi docker_app docker_web
```
