+++
date = "2016-07-27T23:54:46+09:00"
draft = false
slug = "2016-07-27/change-http-to-ssh-on-github"
tags = ["GitHub", "tips"]
title = "GitHubでhttpsでcloneしてしまったリポジトリをsshに変更する"
+++

時々なぜかhttpでcloneしてしまうことがあって、その都度どうやってsshにするんだっけ？となるのでメモ。

# 現在のoriginの状態を確認する

` git remote -v `

# SSHに変更する

` git remote set-url origin git@github.com:USERNAME/OTHERREPOSITORY.git `

# 参考

https://help.github.com/articles/changing-a-remote-s-url/
