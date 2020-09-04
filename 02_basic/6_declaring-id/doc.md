# \$id
$idプロパティを各スキーマの一意の識別子として含めることもベストプラクティスです。とりあえず、あなたが管理しているドメインのURLに設定してください。

## idプロパティとは
1. スキーマの一意の識別子
2. $ref参照が解決されるベースURI

ほとんどの場合、スキーマがダウンロードされる場所を示す\
住所のスキーマはこんな感じになる
```
{ "$id": "http://foo.bar/schemas/address.json" }
```

### $refで$idの使用

$refにidを指定することができるが、以下のような定義をした時に、ローカル環境でもhttp://foo.bar/schemas/person.jsonを参照することがあるので注意する（バリデータの実装依存となる）
```
{"$ ref"： "person.json"}
```

他に#で始まる$idをつけて$refで参照するやり方がある
```
{
  "$schema": "http://json-schema.org/draft-07/schema#",

  "definitions": {
    "address": {
      "$id": "#address",
      "type": "object",
      "properties": {
        "street_address": { "type": "string" },
        "city":           { "type": "string" },
        "state":          { "type": "string" }
      },
      "required": ["street_address", "city", "state"]
    }
  },

  "type": "object",

  "properties": {
    "billing_address": { "$ref": "#address" },
    "shipping_address": { "$ref": "#address" }
  }
}
```