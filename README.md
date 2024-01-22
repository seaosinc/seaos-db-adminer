# Adminer Docker プロジェクト

このプロジェクトには、PHPで書かれたフル機能のデータベース管理ツールである[Adminer](https://www.adminer.org/)を実行するためのDockerfileが含まれています。

## Dockerイメージのビルド

Dockerfileが含まれるディレクトリで以下のコマンドを実行してDockerイメージをビルドします：

```bash
docker build -t adminer -f Dockerfile.adminer .
```

これにより、`adminer`という名前のDockerイメージが作成されます。

## Dockerイメージの実行

Dockerイメージを実行するには、以下のコマンドを使用します：

```bash
docker run -p 8080:8080 adminer
```

これにより、`adminer`イメージからコンテナが開始され、コンテナのポート8080がホストマシンのポート`8080`にマップされます。

## Accessing へのアクセス
コンテナが実行されているとき、`http://localhost:8080`でAdminerにアクセスできます。データベースの資格情報でログインしてデータベースを管理できます。


## イメージをGithub Container Registry（GHCR）にプッシュ
DockerイメージをGCRにプッシュしたい場合、以下のコマンドを使用できます：

```bash
# DockerイメージにGCRレジストリ名をタグ付け
docker tag adminer:latest ghcr.io/seaosinc/adminer:latest

# DockerイメージをGCRにプッシュ
docker push ghcr.io/seaosinc/adminer:latest
```