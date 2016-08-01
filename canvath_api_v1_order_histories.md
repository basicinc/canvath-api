# GET api/v1/order_histories

発注履歴の一覧を取得

## リクエストパラメーター

| Name   | Description                                                                  |
|--------|------------------------------------------------------------------------------|
| limit  | リミット (任意 デフォルト: 20, MAX: 100 ex: limit=50)                        |

## レスポンスの例

```
{
{
    order_histories: [
        {
            order_id: "1",
            base_order_id: null,
            create_date: "2016-07-12 15:00:54",
            item_states: "側表面印刷スマホケース iPhone6/6s コート印刷　",
            titles: "Canvath-スマホケース",
            status: "新規受付",
            price: 980,
            payment_method: "ペイジェント クレジット",
            deliv_uri: null,
            invoice_uri: null
        },
        {
            order_id: "2",
            base_order_id: "11111111aaaaaaaaa",
            create_date: "2016-07-12 15:00:12",
            item_states: "ロンパース ネイビー 80サイズ ガーメントインクジェット印刷(白引き)　",
            titles: "Canvath−ロンパース",
            status: "配送済み",
            price: 13750,
            payment_method: "ペイジェント クレジット",
            deliv_uri: "http://k2k.sagawa-exp.co.jp/p/web/okurijosearch.do?okurijoNo=22222222222222",
            invoice_uri: "https://cart.canvath.jp/pdf/create_pdf.php?order_id=2"
        }
    ]
}
```

## 解説

* order_id - 注文番号
* base_order_id - BASE注文番号
* create_date - 注文日
* item_states -  商品の注文時の状態
* titles - ユーザが設定した商品名
* status - 注文ステータス
* price -  価格
* payment_method - 支払い方法
* deliv_uri - 配送状況確認URL
* invoice_uri - 領収書URL

## エラーレスポンスの例

```
{
  "error":"not_login",
  "error_description":"ログインが完了していません。"
}
```
