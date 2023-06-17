# vscode-flutter-android

DockerとVS Codeを用いた、Android向けアプリケーションのFlutter開発環境です。

## インストール

- git
- Docker
- [VS Code](https://code.visualstudio.com/download)
- [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Templateからのリポジトリ作成

1. GitHubにログインします
1. GitHubのリポジトリを開きます  
https://github.com/jp-rad/vscode-flutter-android
1. `Use this template` をクリックし、リポジトリを作成します  
[こちら - https://github.com/jp-rad/vscode-flutter-android/generate](https://github.com/jp-rad/vscode-flutter-android/generate)

## クローンとVS Codeの起動

1. `git clone <your GitHub Code URL>`
1. git clone したフォルダををVS Codeで開きます
1. Dockerを起動します
1. VS Codeで`Reopen in Container`を実行し、Dockerコンテナーを起動します

## アプリケーション名の変更

Templateでは、アプリケーション名が`myapp`となっていますので、次のファイルの`myapp`の記述を変更します。

- pubspec.yaml  
`name: myapp`、`androidPackage: com.example.flutter.myapp`、`iosBundleIdentifier: com.example.flutter.myapp`
- test\widget_test.dart  
`import "package:myapp/main.dart";`

## 初回ビルド

アプリケーション名を変更後、次の方法で初回ビルドを行い、必要なSDKやプラグインをインストールします。

- メニュー `Terminal` > `Run Build Task... (Ctrl+Shift+B)`

## VS Codeでの開発

1. VS Codeでソースコードを編集します(`lib`フォルダと`test`フォルダ)
1. ユニットテストを実行するには、`Run and Debug (Ctrl+Shift+D)`で、`flutter test`を開始します
1. apkファイルをビルドするには、メニュー `Terminal` > `Run Build Task... (Ctrl+Shift+B)`を実行します
1. 実機等でテスト実行するには、`adb connect`で実機等に接続し、`Run and Debug (Ctrl+Shift+D)`で、`flutter run`を開始します


## 構成ファイル

`.android/app/build.gradle`ファイルや`.android/app/src/main/AndroidManifest.xml`ファイルの内容を追加・変更したい場合は、`.configfiles`フォルダ内にそのフォルダ階層のまま配置してください。
メニュー `Terminal` > `Run Build Task... (Ctrl+Shift+B)`を実行すると、それらのファイルで上書きコピーされ、その後、ビルドが実行されます。
