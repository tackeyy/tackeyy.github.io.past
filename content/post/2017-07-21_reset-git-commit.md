+++
date = "2016-07-21T15:50:21+09:00"
draft = false
slug = "2016-07-21"
tags = ["git", "tips"]
title = "git commitを取り消す"
+++

# 間違えてdevelopにコミットしてもーた

そんな時にいつもコミットの取り消し方をググるので備忘がてらメモ。

# コミットを取り消してワークディレクトリはそのままにする

```
  git reset --soft HEAD^
```

# コミットを取り消してワークディレクトリの内容も書き換える

```
  git reset --hard HEAD^
```


# その他

説明されてるページ見つけた。<br>
http://d.hatena.ne.jp/mrgoofy33/20100910/1284069468
