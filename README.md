# csv2geojson

このリポジトリは、CSV フォーマットのデータを GitHub Actions で GeoJSON に変換し API として公開するためのテンプレートリポジトリです。

## ご利用方法

* [[Use this template]](https://github.com/geoloniamaps/csv2geojson/generate) ボタンをクリックして、このテンプレートを自分のリポジトリにコピーしてください。
* `data.csv` を編集してコミットすると数分後に GeoJSON が生成され、`https://<あなたのGitHubユーザー名>.github.io/<リポジトリ名>/data.json` のような URL でアクセスできます。（[サンプル URL](https://geoloniamaps.github.io/csv2geojson/data.json)）

### Google スプレッドシートで CSV を編集する

1. [こちらのサンプルデータ](https://docs.google.com/spreadsheets/d/125tgFwGwkdEX5rapUMQuzVQ0BPshHkU0K_snFagOzwk/edit#gid=0) ををコピーして、ご自身のデータを入力してください。
2. 入力したデータを CSV でエクスポートして、その内容を `data.csv` に上書きしてください。

緯度経度の取得には、[Community Geocoder](https://community-geocoder.geolonia.com/#12/35.68124/139.76713) をご利用することをご推奨します。

## GitHub Pages の設定方法

* GitHub のリポジトリのメニューの中にある [Settings] をクリックしてください。
* 移動先のページの下の方にある [GitHub Pages] のところで、以下のように設定してください。

![](https://www.evernote.com/l/ABXqA26fEitDNZG6KDxX-Os6Qb8gciGRKSYB/image.png)

## Geolonia Maps での地図の表示方法

* 保存された CSV は GitHub Actions によって、自動的に GeoJSON に変換されます。GeoJSON は、上述のように `https://<あなたのGitHubユーザー名>.github.io/<リポジトリ名>/data.json` のような URL でアクセスできますので、ブラウザで URL を確認した後、その URL をコピーしてください。
* [Geolonia Maps の API キーを取得](https://docs.geolonia.com/tutorial/002/) して、[JavaScript API を設置](https://docs.geolonia.com/tutorial/003/)  してください。
* 地図を表示したい場所に以下のような HTML を設置してください。

```
<div class="geolonia" data-geojson="https://geoloniamaps.github.io/csv2geojson/data.json"></div>
```

### デモ: 

[![](https://www.evernote.com/l/ABXqj0bWP2hLzJ6LkXidrapwc3eJstLY3ScB/image.png)](https://codepen.io/geolonia/pen/RwgJjmE)

https://codepen.io/geolonia/pen/RwgJjmE

[詳細はドキュメンテーションをご参照ください。](https://docs.geolonia.com/tutorial/008/#%E5%A4%96%E9%83%A8%E3%81%AE-geojson-%E3%82%92%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%82%80)

## CSV の各列の解説

* `title` - ここに入力された文字列は、マーカーの下にタイトルとして表示されます。
* `description` - マーカーをクリックした際に、ポップアップで表示させるコンテンツです。
* `lat` - 緯度を指定してください。 (例: `35.6321`)
* `lng` - 経度を指定してください。 (例: `139.8808`)
* `marker-size` - `medium`、`large`、`small` のいずれかを指定してください。
* `marker-color` - マーカーの色を RGB で指定してください。 (例: `#FF0000`)
* `stroke` - マーカーの境界線の色を RGB で指定してください。 (例: `#FFFFFF`)
* `stroke-width` - 境界線の太さ（ピクセル）を数字で指定してください。 (例: `2`)

サンプル CSV は、以下の URL にあります。

https://docs.google.com/spreadsheets/d/125tgFwGwkdEX5rapUMQuzVQ0BPshHkU0K_snFagOzwk/edit#gid=0

データの仕様については、Geolonia Maps のドキュメンテーションもご参照ください。

https://docs.geolonia.com/geojson/