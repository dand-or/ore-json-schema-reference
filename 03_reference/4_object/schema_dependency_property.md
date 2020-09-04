```
{
  "type": "object",

  "properties": {
    "name": { "type": "string" },
    "credit_card": { "type": "number" },
    "billing_address": { "type": "string" }
  },

  "required": ["name"],

  "dependencies": {
    "credit_card": ["billing_address"]
  }
}
```

ok
```
{
  "name": "John Doe",
  "credit_card": 5555555555555555,
  "billing_address": "555 Debtor's Lane"
}
```

```
{
  "name": "John Doe"
}
```

```
{
  "name": "John Doe",
  "billing_address": "555 Debtor's Lane"
}
```

ng
```
{
  "name": "John Doe",
  "credit_card": 5555555555555555
}
```
