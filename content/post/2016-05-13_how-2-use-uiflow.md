+++
date = "2016-05-13T01:41:17+09:00"
draft = false
slug = "2016-05-13/how- 2-use-uiflow"
tags = ["開発ツール", "uiflow", "サイトマップ"]
title = "uiflowを使ってみる"
+++

勉強も兼ねて[この前書いたアイディア](http://blog.tackeyy.org/post/2016-05-13/koreyondoke-com/)を作ってみようかなと思ってます。<br>
まずはサイトマップを書こうと思い、前々から気になったツールを使ってみました。

### uiflow?

[もう保守されない画面遷移図は嫌なので、UI Flow図を簡単にマークダウンぽく書くエディタ作った](http://qiita.com/hirokidaichi/items/ff54a968bdd7bcc50d42)


### インストール

>インストール方法
グラフの生成にはGraphvizを用います。<br>
brewなどを通じてinstallしておいてください。<br>
```brew install graphviz```<br>
```npm install -g uiflow```<br>

@see https://github.com/hirokidaichi/uiflow

インストール方法はREADMEに書いてあります。<br>
npmをインストールしていない場合は、以下のコマンドでnpmをインストール後に上記のREADME通りにすれば、セットアップ完了です。<br>
<br>
npmはnodeに内包されているので、以下の通りにすれば上記の```npm install ~```をたたけるようになります。<br>

* node / npm をインストールする<br>
```brew install node ```<br>

インストールできたかどうかは、以下で確認しました。<br>
```npm --version```<br>
> 3.8.6

### 使い方

もうインストールできたら使い方は迷いません。<br>
ディレクトリはお好きにどうぞ。<br>

1. ```mkdir content```(uiflow直下）
1. ```vim koreyome-com.txt```
1. 何か書く
1. ```uiflow -i koreyome-com.txt -o koreyome.png -f png```
1. uiflow直下にkoreyome.pngができる

[こんな感じ](https://gyazo.com/5bedd4090b3d3b74b88d589ad9472f0a)になります。(READMEの説明をコピーしました。）<br>
もう夜遅いから明日フロー書きます。<br>
<br>
<br>
<br>
<br>
<br>
<br>
ちゃんちゃん。
