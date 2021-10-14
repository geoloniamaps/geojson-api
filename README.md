# GeoJSON API

このリポジトリは、CSV フォーマットのデータを GitHub Actions で GeoJSON に変換し API として公開するためのテンプレートリポジトリです。

Geolonia Maps なら以下のような簡単なマークアップで地図に表示することが可能です。

```
<div class="geolonia" data-geojson="<GeoJSON の URL>"></div>
```

デモ: https://codepen.io/geolonia/pen/RwgJjmE

## ご利用方法

* [[Use this template]](https://github.com/geoloniamaps/geojson-api/generate) ボタンをクリックして、このテンプレートを自分のリポジトリにコピーしてください。
* `example.csv` を編集してコミットすると数分後に GeoJSON が生成され、`https://<あなたのGitHubユーザー名>.github.io/<リポジトリ名>/<ファイル名>.json` のような URL でアクセスできます。（[サンプル URL](https://geoloniamaps.github.io/geojson-api/example.json)）
* 任意のファイル名の CSV を複数設置することも可能です。
* 点データのみに対応しています。

### Google スプレッドシートで CSV を編集する

1. [こちらのサンプルデータ](https://docs.google.com/spreadsheets/d/125tgFwGwkdEX5rapUMQuzVQ0BPshHkU0K_snFagOzwk/edit#gid=0) をコピーして、ご自身のデータを入力してください。
2. 入力したデータを CSV でエクスポートして、それを任意のファイル名でコミットしてください。

緯度経度の取得には、[Community Geocoder](https://community-geocoder.geolonia.com/#12/35.68124/139.76713) をご利用することをご推奨します。

## GitHub Pages の設定方法

* GitHub のリポジトリのメニューの中にある [Settings] をクリックしてください。
* 移動先のページの下の方にある [GitHub Pages] のところで、以下のように設定してください。

![](https://www.evernote.com/l/ABXqA26fEitDNZG6KDxX-Os6Qb8gciGRKSYB/image.png)

## Geolonia Maps での地図の表示方法

* 保存された CSV は GitHub Actions によって、自動的に GeoJSON に変換されます。GeoJSON は、上述のように `https://<あなたのGitHubユーザー名>.github.io/<リポジトリ名>/<ファイル名>.json` のような URL でアクセスできますので、ブラウザで URL を確認した後、その URL をコピーしてください。
* [Geolonia Maps の API キーを取得](https://docs.geolonia.com/tutorial/002/) して、[JavaScript API を設置](https://docs.geolonia.com/tutorial/003/)  してください。
* 地図を表示したい場所に以下のような HTML を設置してください。

```
<div class="geolonia" data-geojson="<GeoJSON の URL>"></div>
```

デモ: https://codepen.io/geolonia/pen/RwgJjmE

[詳しくは Geolonia Maps ドキュメンテーションを御覧ください。](https://docs.geolonia.com/)

## CSV の各列の解説

|列名|必須|デフォルト|内容|
|-|-|-|-|
|`title`|○||ここに入力された文字列は、マーカーの下にタイトルとして表示されます。|
|`lat`|○||緯度を指定してください。 (例: `35.6321`)|
|`lng`|○||`lng` - 必須。経度を指定してください。 (例: `139.8808`)|
|`description`|||マーカーをクリックした際に、ポップアップで表示させるコンテンツです。|
|`marker-size`||`medium`|`medium`、`large`、`small` のいずれかを指定してください。|
|`marker-color`||`rgba(255, 0, 0, 0.4)`|マーカーの色を指定してください。|
|`stroke`||`#FFFFFF`|マーカーの輪郭線の色を RGB で指定してください。|
|`stroke-width`||`2`|境界線の太さ（ピクセル）を数字で指定してください。|

### 備考

* `marker-color` は、`#FF0000` または `rgba(255,0,0)` のように指定することが可能です。
* 列の順番に制約はありません。
* `description` では、HTML も利用可能です。
* 上記にない列は、`properties` に保存されますが、これらの値を利用するには JavaScript によるプログラミングが必要です。
* [サンプル CSV は、こちらにあります。](https://docs.google.com/spreadsheets/d/125tgFwGwkdEX5rapUMQuzVQ0BPshHkU0K_snFagOzwk/edit#gid=0)
* データの仕様については、Geolonia Maps の[ドキュメンテーション](https://docs.geolonia.com/geojson/)もご参照ください。
