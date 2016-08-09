+++
date = "2016-05-14T11:17:05+09:00"
draft = false
slug = "2016-05-14/mailto-slack-from-sideci"
tags = ["Slack", "SideCI"]
title = "SideCIの実行結果をSlackに通知してみる"
+++

### SideCI?

> SideCIはGitHubと連携し、自動的に解析ツールを利用したコードレビューを行うサービスです。<br>

[Getting started with SideCI](https://www.sideci.com/ja/docs/getting-started)<br>


### SideCIはSlack連携できない？

SlackのアプリでSideCIがでてこない（GitHubやCircleCIなどは出る）ので、<br>
未対応なのかなと思いSideCIの中の人に問い合わせてみました。<br>

>申し訳ありませんが現在はSlackなどを含めた外部ツールへの通知はサポートしておりません。。
間接的にではありますが、 `GitHubに対してのPR/コメント通知をSlack連携` することにより、SideCI経由でのコメントの付記のタイミングはSlackで受け取ることは可能です。

と回答をいただきました。<br>

余談ですが、問い合わせがチャットなので問い合わせ時の心理的な障壁もあまりなく問い合わせができました。<br>
（チャットの問い合わせ流行りそう。）<br>
また、レスポンスも早くとても好印象でした。<br>

### SlackとGitHubの連携

1. SlackのApp Directoryに行きます（Slack左上のチームからApps & integrationsを選択）
1. 真ん中の検索窓にGitHubと入力して、GitHubをインストールします（もちろんインストール済みの場合は必要ありません）
1. App DirectoryのGitHubのアプリに移動すると"チーム名 configure"があるので、configureを選択します
1. [Add Configuration](https://gyazo.com/7b66e42aabe7bfc86e27651ca4e44d0b)をクリックします
1. ここまでくれば、説明にそってRepositories, Events, Channelを設定すればOKです（今回はSideCIでpull requestにコメントが付けられた時をトリガーにしたいので、"New comment on issue or pull request"にチェックをつけます）


### よもやま話

"New comment on issue or pull request"にチェックをつけたのに、<br>
なぜか"Nothing is configured"が表示されてSlackに通知が飛びませんでした。<br>
<br>
Slackに問い合わせみたところ[すぐ返信きた](https://gyazo.com/bb6183e3da2c1f76d86ebfb355f5b5db)。<br>
（金曜日だったので、時差を考慮してもどーせ来週前半に回答くれるんでしょと思ってた...）<br>

やっぱりレスが早いと気持ちユーザー体験ができるんだなと思いました。<br>
今回に関してはこちらの期待が低かったこともありますけどね。<br>

<br>
<br>
<br>
<br>
<br>

ちゃんちゃん。
