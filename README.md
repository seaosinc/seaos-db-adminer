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
docker run -p <ポート>:8080 adminer
```

<<<<<<< HEAD
これにより、`adminer`イメージからコンテナが開始され、コンテナのポート`8080`がホストマシンのポート`8080`にマップされます。
=======
これにより、`adminer`イメージからコンテナが開始され、コンテナのポート`8080`がホストマシンの任意の利便性のあるポートにマップされます。`<ポート>`をホストマシンで利用可能なポートに置き換えてください。
>>>>>>> 5a0d208 (Update readme.md)

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
