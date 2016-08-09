+++
date = "2016-05-20T14:29:04+09:00"
draft = false
slug = "2016-05-20/upload-file-to-local-with-carrierwave"
tags = ["rails", "gem", "carrierwave"]
title = "carrierwaveを使ってlocalに画像をuploadする"
+++

備忘のために[carrierwave](https://github.com/carrierwaveuploader/carrierwave)を使って、ローカルに画像をアップロードする手順を記しておきます。<br>

* rails 4.2<br>

### 手順

GemのREADMEに記載があるのでインストールは飛ばします。<br>
詳しい手順はREADMEや[ここ](http://morizyun.github.io/blog/carrierwave-image-uploader-rails/)などにもあります。<br>

### 1.コントローラーを作る

ポリモーフィック関連で実装しているので、imageという名前でuploaderを作成します。
<br>
```rails generate uploader image```
<br>

最小限の機能で良いので、上記のコマンドで作成されたimage_uploader.rbを[こんな感じ](https://gyazo.com/f490ad33743aabb0123119a873feb330)にします。<br>
image_uploader.rbのパスは画像の左下に出てます。<br>

### 2.モデルを修正する

以下の★ の箇所を追記します。

```
class Image < ActiveRecord::Base
  acts_as_paranoid

  ★ mount_uploader :image, ImageUploader
  belongs_to :imageable, polymorphic: true
  ★ belongs_to :user, polymorphic: true
end
```

なぜかmodels/userにuploaderをmountしていたので、Images.imageに#ActionDispatch::Http::UploadedFileほにゃららという文字列が入ってうまく画像をupdateできずに相当はまりました...<br>

### 3. ビューを修正する

views/users/_form.html.erb<br>

user has one image なので、user.image.image_urlで画像のURLを取得します。<br>
has_manyの場合は、user.images.first.image_urlとかeachでimagesを回してimage_urlとかでURLが取得できます。<br>

```
<% if user.image.image_url.nil? %>
  <%= image_tag 'no_image.jpg', size: '270x300' %>
  <%= f.file_field :image %>
  <% else %>
  <%= image_tag user.image.image_url %>
<% end %>
```

#### 画像を削除する

READMEに記載がある通り、remove_imageを使います。<br>
viewを以下の通りにするだけで保存時に画像が削除されます。<br>
```
<label>
  <%= check_box :remove_image, user.image.remove_image %>
  画像を削除する
</label>
```


#### TODO

* 画像アップロード時にプレビューを表示する<br>
  * 以下を試してみる
http://morizyun.github.io/blog/carrierwave-image-uploader-rails/
* 画像削除のチェックボックスにレが入った時に画像を見えなくする<br>

<br>
<br>
<br>
<br>
<br>

ほいじゃあの
