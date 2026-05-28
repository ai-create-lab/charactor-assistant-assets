# Character Assistant Assets

アプリ配信用アセットリポジトリ。GitHub Releases 経由で CDN 配信する。

## manifest.json

アプリが起動時に取得するアセットマニフェスト。各アセットのバージョン・URL・SHA256 を管理。

## アセット更新手順

1. 新しいアセットファイルを用意
2. `manifest.json` のバージョンと URL を更新
3. GitHub Release を作成し、アセットファイルをアップロード

## STT モデルの R2 配信

`.github/workflows/publish-stt-r2.yml` を GitHub Actions から手動実行すると、
指定した Release asset を検証して Cloudflare R2 にアップロードする。

必要な repository secrets:

```text
R2_ACCESS_KEY_ID
R2_SECRET_ACCESS_KEY
R2_S3_ENDPOINT
R2_BUCKET_NAME
```

現在のアプリ側固定キー:

```text
models/reazonspeech-nemo-v2.gguf
```

workflow の summary に `size` / `sha256` が出るので、
`charactor-assistant/backend/workers/src/routes/assets.ts` の
`stt_reazonspeech_v2` に同じ値を反映して Worker をデプロイする。
