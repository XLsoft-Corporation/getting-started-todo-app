# Todoアプリの始め方

このプロジェクトは、ToDoリストアプリケーションのサンプルを提供します。ComposeファイルからDockerfile、GitHub Actionsを使用したCI、そしてテストの実行に至るまで、現在のDockerに関するベストプラクティスをすべて紹介しています。誰でもすぐに取り組んで簡単に学べるよう、詳細なドキュメントを用意しています。

## アプリケーションアーキテクチャー

![image](https://github.com/docker/getting-started-todo-app/assets/313480/c128b8e4-366f-4b6f-ad73-08e6652b7c4d)


このサンプルアプリケーションは、Node.jsのバックエンドからデータを受け取るシンプルなReactフロントエンドです。

アプリケーションがパッケージ化されて配布される際、フロントエンドは静的なHTML、CSS、JSにコンパイルされ、バックエンドとバンドルされて静的アセットとして配信されます。つまり、このサンプルアプリではサーバーサイドレンダリングは行われていません。

開発中は、バックエンドとフロントエンドで必要な開発ツールが異なるため、これらは2つの別々のサービスに分割されています。これにより、[Vite](https://vitejs.dev/) がReactアプリを管理し、[nodemon](https://nodemon.io/) がバックエンドを処理できるようになります。コンテナを使えば、開発上の要件を簡単に分離できます！

## 実行

プロジェクトを起動するには、Docker Desktop をインストールし、以下のコマンドを実行するだけです：

```
git clone https://github.com/xlsoftkk/getting-started-todo-app
cd getting-started-todo-app
docker compose up --watch
```

Docker Hub からいくつかのコンテナイメージがダウンロードされ、しばらくするとアプリケーションが起動して動作し始めます！お使いのマシンに何かをインストールしたり設定したりする必要はありません！

[http://localhost](http://localhost) にアクセスするだけで、アプリが動作しているのを確認できます！

バックエンドやフロントエンドに加えた変更は、コンテナを再構築したり再起動したりすることなく、即座に反映されます。

データベースの運用を支援するため、開発スタックにはphpMyAdminも含まれており、
[http://db.localhost](http://db.localhost) からアクセスできます（ほとんどのブラウザでは
`*.localhost` が正しく解決されるため、hosts ファイルの変更は必要ないはずです）。

### 終了処理

作業が完了したら、次のコマンドを実行してコンテナを削除してください：

```
docker compose down
```
