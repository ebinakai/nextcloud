# Nextcloud on Docker

## Prepare

.env に諸項目を設定する。

```bash
# 機密情報の設定
vim .env
```

```env
MYSQL_ROOT_PASSWORD=
MYSQL_DATABASE=
MYSQL_USER=
MYSQL_PASSWORD=
NEXTCLOUD_PORT=
GID=
```

> [!NOTE]
> GIDは外部ストレージをマウントする際にアクセス権限で引っかからないために、マウントするディレクトリの所有グループのIDを設定。

## Installation

マウントする外部ストレージがあれば、 `docker-compose.yaml` ファイルの `volumes` に記載する。ない場合は、そのフィールドを削除すること。

```bash
# サービスの起動
docker-compose up -d --build
```

> [!IMPORTANT]
> アクセスする際はSSLで接続しないと警告が出るので、このサービスの前面に置くプロキシでHTTPS通信をすること。  
> また、プロキシ先は、nextcloudコンテナではなく、このプロジェクトのnginxコンテナ80番ポートに接続する。
