+++
date = "2016-05-17T15:25:25+09:00"
draft = false
slug = "2016-05-17/add-ssh-key-to-github"
tags = ["GitHub", "公開鍵"]
title = "GitHubにSSH公開鍵をやっと登録した"
+++

git pullなどをするときに常にuser/passを聞かれるのが面倒だったので、<br>
公開鍵を登録しなきゃなと思っていたのですが、後回しになっていました。<br>

#### 手順
1. 公開鍵を作成（すでに作成している場合はスキップ）

1. GitHubにSSH公開鍵を登録
1. 接続確認

一通り説明してある[ページ](dhttp://monsat.hatenablog.com/entry/generating-ssh-keys-for-github)がありました。説明通りやれば簡単にできるので、そちらを参考してください。

#### はまったところ

##### SSH公開鍵をGitHub上に設定して ```ssh -T git@github.com```で接続確認ができたのに、```git push```などのコマンド実行時にuser/passを聞かれる

そもそもcloneする時にhttpsだったため、SSHでの通信を行ってませんでした。<br>

1. ```git remote -v```でhttpsになっていることを確認<br>
1. ```git remote set-url origin git@github.com:{user_name}/{repository_name}git``` [refs](https://help.github.com/articles/changing-a-remote-s-url/)


##### ```git pull origin develop```する時にポップアップダイアログで「id_rsaのパスワードを入力してください」と聞かれる

そもそも公開鍵を作成する時にパスフレーズは入力していない（つもり）だったし、パスフレーズ=パスワードかどうかわかりませんでした。<br>
パスフレーズを入力していないとパスワードを尋ねられないみたいなので、パスフレーズで何かしら入力してしまってたのだと思います。<br>
手順としては微妙ですが、やったとこは以下の通り。<br>

1. パスフレーズの変更 ```ssh-keygen -p```
1. パスフレーズ入力を省略```ssh-add ~/.ssh/id_rsa```


```ssh-add```は<br>

>ssh-add は認証エージェントであるssh-agent (1) に、秘密鍵を追加します。（省略）
パスフレーズが必要な場合、ssh-add はユーザにそれを尋ねます。このパスフレーズはユーザの端末から読み込まれます。複数の identity ファイルが指定された場合、ssh-add は最後に入力されたパスフレーズをくり返し使います。

<br>
http://euske.github.io/openssh-jman/ssh-add.html<br>

とのこと。


#### 気になったこと

* [このアドレス](https://gyazo.com/1529b6da7236385b0e6b4495385b0080)なに？（塗りつぶしてあったよく見えませんが、最後のmba.localみたいなやつ）

ssh-keygenコマンドにオプションをつけずに実行すると、ユーザー名@ホスト名.ドメインネームになるらしい。<br>
何かメールが送られたりするのか？そしたらメールアドレスを変更したい。<br>
と思ったが、ただのコメントだった。<br>
http://euske.github.io/openssh-jman/ssh-keygen.html<br>

なので直接編集しました。


#### メモ

http://d.hatena.ne.jp/hnw/20140705


<br>
<br>
<br>
<br>
<br>
<br>
<br>

ほいじゃあの。
