# POST order

API経由で直接Cartに商品を入れる

## リクエストパラメーター
addressモードにすると、デフォルトで配送情報をセットすること出来ます。<br>
addressモードにする場合はパラメータにmode=addressを追加してください。<br>
電話番号、郵便番号はハイフン抜きで指定してください。


| Name   | Description                                                      |
|--------|------------------------------------------------------------------|
| item_id | 商品ID (必須 ,ex: 11111111aaaaaaaaa)                            |
| num     | 発注個数 (任意,ex: 10)                     　　　　　　　　     |
| mode    | addressモードの判定 (任意 ,ex: address)                 　　　　|
| name01  | 姓 (addressモードの場合は必須 ,ex: 山田)                        |
| name02  | 名 (addressモードの場合は必須,ex: 太郎)                         |
| pref    | 都道府県 (addressモードの場合は必須,ex: 東京都)                 |
| addr01  | 住所1 (addressモードの場合は必須,ex: 千代田区一番町)            |
| addr02  | 住所2 (addressモードの場合は必須,ex: 17-6一番町MSビル1F)        |
| tel     | 電話番号 (addressモードの場合は必須,ex: 0332210311)             |
| zip     | 郵便番号 (addressモードの場合は必須,ex: 1020082)                |



## エラーレスポンスの例
```
{
  "error":"system_error", 
  "error_description":"システムエラーが発生しました"
}
```
```
{
  "error":"not_login",
  "error_description":"ログインが完了していません"
}
```
```
{
  "error": "exist_item", 
  "error_description": "存在しない商品IDです"
}
```
```
{
  "error":"parameter_shortfall", 
  "error_description": "必要なパラメータが不足しています"
}
```
```
{
  "error":"not_zip", 
  "error_description": "郵便番号に数字以外が含まれています"
}
```
```
{
  "error":"exist_pref", 
  "error_description": "該当する都道府県がありません"
}
```

```
{
  "error":"not_tel", 
  "error_description": "電話番号に数字以外が含まれています"
}
```
