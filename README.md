# Docker Playgorund - kali

コンテナ上でkalilinuxの実行環境を構築しVisual Studio Codeから接続・実行できる環境を提供する

コンテナイメージのベースは
[kalilinux/kali-rollong:latest](https://hub.docker.com/_/python)
を利用。最新の環境としている。

追加で以下をインストールしている

* `python3`
* `python3-pip`
* `git`
* `curl`

実行ユーザ:`vscode`  
ワークスペース:`/workspace`  

ホスト側の`workspace`フォルダをコンテナ側の`/workspace`としてマウントしている

pipで以下をインストール済み

* flake8
* autopep8

以下のVisual Studio Code 拡張をインストール

* EditorConfig.EditorConfig
* ms-python.python
* ms-python.flake8
* ms-python.autopep8
* njpwerner.autodocstring

## 使い方

[Docker Desktop](https://www.docker.com/products/docker-desktop/)を立ち上げる

[Visual Studio Code](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)に[Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)をインストール

後は Dev Containerで起動する
