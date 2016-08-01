# GET GET api/v1/materials

商品情報の一覧を取得

## リクエストパラメーター

| Name   | Description                                                                  |
|--------|------------------------------------------------------------------------------|
| item_id  | item_idを指定することで任意の商品の情報のみ習得出来る(任意 ex:item_id=00000000000aaaaaaaaaaaaa)|
| category   | categoryを指定することで任意の情報のみ習得出来る(任意 ex: category=phonecase) |                                                                    |
| limit  | リミット (任意 デフォルト: 20, MAX: 100 ex: limit=50)                        |

## レスポンスの例

```
{
    items: [
        {
            item_id: "579ae479766167115d110000",
            category: "vtshirt",
            title: "VネックTシャツ",
            price: 2200,
            create_date: "2016-07-29 14:07:05",
            images: {
                original: "https://canvath.s3.amazonaws.com/uploads/material/image/579ae479766167115d110000/images.jpg",
                print: "https://canvath.s3.amazonaws.com/uploads/item/vtshirt/print/579ae485766167115d120000/jpg20160729-4396-1scrw06.png",
                thumbnail: "https://canvath.s3.amazonaws.com/uploads/item/vtshirt/gray/579ae485766167115d120000/jpg20160729-4445-tfb5c4.png"
            },
            types: {
                key: "gray",
                type: "toner",
                size: "l",
                cut: null
            }
        },
        {
            item_id: "579ab33d76616710e7030000",
            category: "ladystshirt",
            title: "レディースTシャツ",
            price: 2200,
            create_date: "2016-07-29 10:37:01",
            images: {
                original: "https://canvath.s3.amazonaws.com/uploads/material/image/579ab33d76616710e7030000/image.jpeg",
                print: "https://canvath.s3.amazonaws.com/uploads/item/ladystshirt/print/579ab34676616710e7040000/jpg20160729-4277-1mxbwot.png",
                thumbnail: "https://canvath.s3.amazonaws.com/uploads/item/ladystshirt/gray/579ab34676616710e7040000/jpg20160729-4327-1sce4ux.png"
            },
            types: {
                key: "gray",
                type: "toner",
                size: "l",
                cut: null
            }
        }
    ]
}
```

## 解説

* item_id - 商品を識別するユニークなID
* category - 商品の種別
* title - ユーザが設定した商品名
* price - 商品の値段 (税込み)
* create_date - 商品の作成日
* images - 商品の画像
  * original - ユーザが投稿したオリジナルの画像
  * print - 商品印刷用に変換した画像
  * thumbnail - 商品のサムネイル画像
* types - 商品の色画像
  * key -  機種、色
  * type - 印刷方式
  * size - サイズ
  * cut - ステッカーのりんごマークありなし

## エラーレスポンスの例

```
{
  "error":"not_login",
  "error_description":"ログインが完了していません。"
}
```
```
{
  "error":"invalid_parameter",
  "error_description":"指定外のパラメータを検知しました。"
}
```
