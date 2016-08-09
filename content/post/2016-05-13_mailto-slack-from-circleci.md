+++
date = "2016-05-13T12:02:49+09:00"
draft = false
slug = "2016-05-13/mailto-slak-from-circleci"
tags = ["CircleCI", "Slack"]
title = "CircleCIの実行結果をSlackに通知してみる"
+++

### CircleCI?

[継続的インテグレーション](https://ja.wikipedia.org/wiki/%E7%B6%99%E7%B6%9A%E7%9A%84%E3%82%A4%E3%83%B3%E3%83%86%E3%82%B0%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3)のプラットフォームです。

https://circleci.com/<br>

前はJenkins(Hudson)を使っていたので、Jenkins的なやつと理解しています。<br>
特にWeb系は流行り廃りがあるのであれですが、JenknsからCircleCIに移行する流れもあるっぽい？です。<br>

[Jenkinsと完全にサヨナラして、CircleCIに移行した話](http://blog.stormcat.io/entry/2015/07/02/150000)

### Slackとの連携

概要は[こちら](https://circleci.com/blog/slack-integration/)でおおよそ把握できます。<br>
ぼくが唯一ハマったのは、chat notificationの設定箇所が見つけられなかったところだけです。（10分くらい探しました。。）<br>


* SlackでCircleCIと連携する設定

Channelの[左上](https://gyazo.com/304cd41890db875b1e121a6eace1ab0d)からApps & integrationsを選択します。<br>
画面遷移後にCircle CIを検索して、notificationを送信したい[チームを選択](https://gyazo.com/77053b3ed12ab7179a484227ca08d06f)します。<br>

*すでに設定しているので上の画像では、configureになっています<br>
*team選択後にchannelを選択できます<br>
<br>

ここからはSlack上に説明があるので、それに沿ってCircleCI側の設定をしてください。<br>


* CircleCI側の設定

最初の[リンク](https://circleci.com/blog/slack-integration/)の通りです。<br>
設定箇所へたどり着くには、[ここ](https://gyazo.com/324c92ff27b547843291c71c1086c1e2)の歯車をクリック後に<br>
ダッシュボードの中央左のChat NotificationsからSlackで説明されていた設定（URL貼るだけですが）を行います。<br>
記載してありますが、Fixed/Failed Onlyにチェックを入れると、ビルド失敗/修正だけがNotificationのトリガーになります。<br>
<br>
<br>
<br>
<br>
ちゃんちゃん。
