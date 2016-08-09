+++
date = "2016-06-14T20:28:37+09:00"
draft = false
slug = "2016-06-14/monkey-patch"
tags = ["モンキーパッチ", "rails", "Ruby"]
title = "モンキーパッチ"
+++

社内の方が[gmo-payment-ruby](https://github.com/t-k/gmo-payment-ruby)にあてたモンキーパッチを紹介されていました。<br>
前職ではJavaを主に使っていて、外部のライブラリを使用するというよりも自社で自社仕様のライブラリを使う（もしくは作る）方が多かったので、<br>
今回初めてモンキーパッチという言葉を聞きました。<br>

#### モンキーパッチ

> モンキーパッチは、オリジナルのソースコードを変更することなく、実行時に動的言語(例えばSmalltalk, JavaScript, Objective-C, Ruby, Perl, Python, Groovy, など)のコードを拡張したり、変更したりする方法である。
[Wiki](https://ja.wikipedia.org/wiki/%E3%83%A2%E3%83%B3%E3%82%AD%E3%83%BC%E3%83%91%E3%83%83%E3%83%81)

#### 方法

* 紹介されたモンキーパッチでは、class_eval, module_eval (Module)を使用して実装していました<br>
http://ref.xaio.jp/ruby/classes/module/class_eval

#### 話を受けて思ったこと

* モンキーパッチが呼び出されていることをコード見ただけでわかるか？<br>
運用・保守を行うフェーズを想定すると上記の観点を満たせるか、という点が大事になる気がしました。<br>
