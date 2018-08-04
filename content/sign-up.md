## Sign-up

### Store Categories

List all store categories.

```endpoint
GET /api/sign-up/store-categories
```

#### Example request

```curl
$ curl http://192.169.243.65:8080/api/sign-up/store-categories
```

#### Example response

```json
[
  {
      "_id": "5b5722daea455b22f01d6c2c",
      "category_number": 1,
      "category_name": "test_mykola",
      "display_name": "test mykola"
  },
  {
      "_id": "5b572426ea455b22f01d6c2e",
      "category_number": 2,
      "category_name": "rinesh_store",
      "display_name": "rinesh_store"
  }
]
```

### Store Types

List all store types.

```endpoint
GET /api/sign-up/store-types
```

#### Example request

```curl
curl http://192.169.243.65:8080/api/sign-up/store-types
```

#### Example response

```json
[
  {
      "_id": "5b604a8d39b57d0bd0a6072e",
      "name": "public",
      "number": 1
  },
  {
      "_id": "5b604aa239b57d0bd0a60730",
      "name": "branded",
      "number": 2
  }
]
```

### Signing Up Merchant

```endpoint
POST /api/sign-up/merchant
```

#### Example request

```curl
curl -X POST http://192.169.243.65:8080/api/sign-up/merchant
```

#### Example request body

```json
{
"email_id":"a@gmail.com",
"mobile": {
		"dialing_code": 91,
		"number": "458697584"
	}
}
```

Property | Description
---|---
`email_id` | (required) email address
`mobile.dialing_code` | (required) phone number dialing_code
`mobile.number` | (required) phone number

#### Example response

```json
{
    "code": 200,
    "user_id": "5b65eba67ae87956eade18a7"
}
```

### Signing Up Merchant Validation
Finishing the merchant signing up

```endpoint
POST /api/sign-up/merchant/verify
```

#### Example request

```curl
curl -X POST http://192.169.243.65:8080/api/sign-up/merchant/verify
```

#### Example request body

```json
    "user_id":"5b65e5e3873aff52a1a92f16",
	"email_code":398980,
	"mobile_code":210065,
	"password": "111111111"
```

Property | Description
---|---
`user_id` | (required) merchant id
`email_code` | (required) verificaion code from email
`mobile_code` | (required) verification code from sms (not implemented) 
`password` | (required) password

#### Example response

```json
{
    "code": 200,
    "status": true
}
```

### Signing Merchant Validation
Finishing the merchant signing up

```endpoint
POST /api/sign-up/merchant/verify
```

#### Example request

```curl
curl -X POST http://192.169.243.65:8080/api/sign-up/merchant/verify
```

#### Example request body

```json
    "user_id":"5b65e5e3873aff52a1a92f16",
	"email_code":398980,
	"mobile_code":210065,
	"password": "111111111"
```

Property | Description
---|---
`user_id` | (required) merchant id
`email_code` | (required) verificaion code from email
`mobile_code` | (required) verification code from sms (not implemented) 
`password` | (required) password

#### Example response

```json
{
    "code": 200,
    "status": true
}
```

### Signing Up Store

```endpoint
POST /api/sign-up/store
```

#### Example request

```curl
curl -X POST http://192.169.243.65:8080/api/sign-up/store
```

#### Example request body

```multipart/form-data
    json:{"merchant_id": "5b65e5e3873aff52a1a92f16", "store_type": 1, "category_id": "5b63001a21fc9f1314219f29", "display_name": "Sai Super Market", "store_name": "sai_super_market", "mobile": [{"dialing_code": 91, "number": "458697584", "code": 784589, "is_primary": true }, {"dialing_code": 91, "number": "4859658745", "code": 748596, "is_primary": false }], "location": {"type": "point", "coordinates": [11.2563, 114.523], "address": "JVL Plaza, Teynampet", "city": "Chennai", "state": "Tamil Nadu", "zipcode": "600018", "country": "INDIA"}, "refund": {"is_accepted": true, "days": 15 }, "replacement": {"is_accepted": true, "days": 10 }, "delivery": {"radius": 10, "type": 1, "from": "10:00:00", "to": "21:00:00", "other_locations": {"is_enabled": true, "countries": ["AUS", "ENG"], "type": 1 } }, "private": {"is_enabled": true, "settings": "Will be added in the future"} }
    image_1: file
    image_2: file
    image_3: file
    image_4: file
    image_5: file
```

Property | Description
---|---
`json` | (required) store json string
`image_n` | (required) store images


#### Example response

```json
{
    "code": 200,
    "status": true
}
```