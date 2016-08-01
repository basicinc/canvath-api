# Canvath API ドキュメント (β版)
CanvathのAPIの開発者向けのドキュメントです。

## 概要
このAPIを使うと、あなたのアプリケーションとCanvathを連携させることができます。

## 認証
Canvathのログイン機能を使用しています。
APIを使用する前に必ずログイン状態を確認してください。

## 機能
* Canvathで製作した商品情報の一覧を取得する
* Canvathでの発注履歴の一覧を取得する
* API経由で直接Cartに商品を入れる

※ APIは今後も順次心機能を実装していく予定です。

## 仕様

### レスポンス

JSON形式でレスポンスを返します。

正常な場合はHTTPステータスコード 200 OKを返します。

エラーの場合はHTTPステータスコード 400 Bad Requestを返します。

エラーレスポンスの例

```
{
  "error": "not_login",
  "error_description": "ログインが完了していません"
}
```

## API

### materials

* [GET api/v1/materials](canvath_api_v1_materials.md) - 商品情報の一覧を取得

### order_histories

* [GET /api/v1/order_histories](canvath_api_v1_order_histories.md) - 発注履歴の一覧を取得

### order

* [POST /order](canvath_api_v1_order.md) - API経由で直接Cartに商品を入れる

## 注意点

Canvath APIは現在β版のため仕様が変更される場合があります。

## お問い合わせ

[https://support.canvath.jp/hc/ja/requests/new](https://support.canvath.jp/hc/ja/requests/new)
