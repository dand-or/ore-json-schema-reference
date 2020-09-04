- $refとallOf/anyOf/oneOfを組み合わせて拡張表現ができる
- 重複をなくすなど便利

```
// $refを含む住所情報を追加した定義
"shipping_address": {
  "allOf": [
    // Here, we include our "core" address schema...
    { "$ref": "#/definitions/address" },

    // ...and then extend it with stuff specific to a shipping
    // address
    { "properties": {
        "type": { "enum": [ "residential", "business" ] }
      },
      "required": ["type"]
    }
  ]
}
```

