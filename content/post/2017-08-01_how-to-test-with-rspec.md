+++
date = "2016-08-01T23:37:50+09:00"
draft = false
slug = "2016-08-01/rspec-template"
tags = ["Rails", "Rspec", "FactoryGirl", "WebMock"]
title = "Rspecでテストを書くときの雛形"
+++
最近Rspecでテストを書くことが増えているのですが、特別な処理がない限りある程度テスト内容が大体同じなのでは？と思っています。<br>
処理がほぼ同じなのであれば、雛形があった方が実装が早いので、雛形をメモしておく次第です。<br>

携わっているプロジェクトのコードですが、以下の点より業務に影響がないと判断しています。<br>
* adminは大体どのプロジェクトでも存在している（かつ特殊な処理を書いてない）<br>
* プロジェクトが特定される内容がない

# spec/controllers/**/**.rb

## 普通のspecテストの雛形

<script src="https://gist.github.com/tackeyy/12d39610347ec2538481a18ce28d5ae5.js"></script>

## Rspec x FactoryGirl

<script src="https://gist.github.com/tackeyy/f62dc34f6c037f6edde8fa8cbef05110.js"></script>

# spec/models/*.rb

## 普通のspecテストの雛形

<script src="https://gist.github.com/tackeyy/8ce63b57638f2fc58f046e2b63a23f70.js"></script>

## Rspec x FactoryGirl x WebMock

<script src="https://gist.github.com/tackeyy/05e71aadfa4cdbee157820c8553a2111.js"></script>

