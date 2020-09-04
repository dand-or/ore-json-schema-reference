```
"additionalProperties": false
```

- デフォルトはtrue
- trueの場合、定義にないプロパティがあっても許容。falseの場合、定義にないプロパティがあったらNGとする。

```
"additionalProperties": { "type": "string" }
```

- オブジェクトが指定された場合は記載されてない任意のスキーマを検証するための記載と解釈する
- この場合stringの追加プロパティはOKとする