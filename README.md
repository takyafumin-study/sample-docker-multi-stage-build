# sample-docker-multi-stage-build

Dockerfileのマルチステージビルドを試す

## 使い方

### 環境構築

git cloneした後、以下のコマンドで環境構築する

```bash
./run.sh init
```

### production用ビルド

```bash
./run.sh build:prod
```

## 環境

### dockerコンテナ

| コンテナ名 |  説明   |
| ---------- | ------- |
| app        | nginx   |
| web        | php-fpm |

### 機能

|    機能     |        URL        |
| ----------- | ----------------- |
| Laravel App | http://localhost/ |
