---
layout : post
title  : "Dockerに慣れる : コンテナの使われ方"
date   : 2020/06/24
lastchange : 2020-06-24 13:51:12
tags   :
  - docker
  - httpd
  - container
---

## コンテナの使われ方がいくつかありそう

いろいろ調べているとコンテナの使われ方がいくつかありそうだということに気がついたので、それをまとめておく

### 開発用環境

依存関係の問題などで、昨今は仮想環境を作成して開発することがほとんど？ なような気がする。
仮想環境が必要になるのは `rbenv` や `pyenv` と言語領域だけではなく、どうやらOSとしても必要になっているようだ。

1. 開発用コンテナをビルドし
2. 開発領域をマウント
3. その中で開発を行う

みたいな例を見かける。確かに Docker で開発用環境を共有したり保存したりできれば、 _Dockerfile_ や
_docker-compose.yml_ だけで開発環境の共有や移植が行えるので楽、なのかな？


### 本番環境とテスト環境

サービスを実働させる本番環境と、本番環境と同一のテスト環境として利用している。
各種サーバサービスのコンテナが存在するのは主にこのためではなかろうか。

