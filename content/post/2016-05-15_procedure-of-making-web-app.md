+++
date = "2016-05-15T01:57:31+09:00"
draft = true
slug = "2016-05-15/procedure-of-making-web-app"
tags = ["ウェブサービス", "作業記録"]
title = "これよめ.com 〜開発の準備〜"
+++

この前の[記事](http://blog.tackeyy.org/post/2016-05-13/koreyondoke-com/)をとりあえず形にしようと思い開発を始めました。<br>
作業記録としてやった内容をおおまかに記載します。<br>

### 開発ことはじめ

1. GitHubにリポジトリを作った<br>
1. ローカルにcloneした<br>
1. ```rails new .``` した<br>
1. gemを抜き差しした<br>
1. admin周りのベースを作った
  1. ```rails generate admin_lte2```
1. user周りのベースを作った<br>
  1. ```rails g sorcery:install```
  1. ```rake db:migrate```
  1. ```rails g scaffold user email:string crypted_password:string salt:string --migration false```
