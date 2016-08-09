+++
date = "2016-06-14T20:12:54+09:00"
draft = false
slug = "2016-06-14/hugo-commands"
tags = ["hugo"]
title = "Hugoのコマンド3選"
+++

### 普段使う（というよりもこれ以外使ってない）コマンド3選

* 記事追加<br>

```
hugo new post/yyyy-mm-dd_title.md
```

年月日は好みで入れてます。<br>

* サーバー起動<br>

```
hugo server -t angels-ladder -D -w
```

-D ・・・ ドラフトも起動する<br>
-W ・・・ 保存時にページをリロード<br>
angels-ladder ・・・ layout名


* デプロイ

```
hugo -t angels-ladder
```

