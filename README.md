# Character Assistant Assets

アプリ配信用アセットリポジトリ。GitHub Releases 経由で CDN 配信する。

## manifest.json

アプリが起動時に取得するアセットマニフェスト。各アセットのバージョン・URL・SHA256 を管理。

## アセット更新手順

1. 新しいアセットファイルを用意
2. `manifest.json` のバージョンと URL を更新
3. GitHub Release を作成し、アセットファイルをアップロード
