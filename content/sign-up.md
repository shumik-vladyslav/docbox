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

#### Signing up First step
Sending email and phone number. After this useer mast check his email box.

```endpoint
POST /api/sign-up
```

#### Example request

```curl
curl -X POST http://192.169.243.65:8080/api/sign-up
```

#### Example request body

```json
{
	"email_id": "vagi@travala10.com",
	"phone_number": "8927931723"
}
```

Property | Description
---|---
`email_id` | (required) email address
`phone_number` | (required) phone number

#### Example response

```json
{
    "code": 200,
    "message": "Email Verification Code is sended to the customer email"
}
```

#### Signing up Finish step
Finishing the signing up

```endpoint
POST /api/sign-up/finish
```

#### Example request

```curl
curl -X POST http://192.169.243.65:8080/api/sign-up/finish
```

#### Example request body

```json
{
	"password":"password",
"email_verification_code":"ac2f6694777a770e786cd49195f90275692ee65a1d2695a21ec69a05a09f493aa9896c0d67f3a7ead875c62a959acd764621d99ca4d3b0a345672651e055dfe09271955759e1149bf5a7fcb48b4a0aaa97c1280cc259fe821eaf8f818986262a",
"sms_verification_code":"sms_verification_code",
"private_shop_request":"private_shop_request",
"other_location":"other_location",
"other_location_delivery_by":"other_location_delivery_by",
"delivery_by":"delivery_by",
"dilivery_time_from":"dilivery_time_from",
"delivery_time_to":"delivery_time_to",
"delivery_distance":"delivery_distance",
"refaund_within":"refaund_within",
"product_replacement_within":"product_replacement_within",
"pincode":"pincode",
"state":"state",
"city":"city",
"country":"country",
"address":"address",
"mobile_number":"mobile_number",
"secondary_mobile_number":"secondary_mobile_number",
"store_name":"store_name",
"store_category":"store_category",
"store_type":"store_type"
}
```

Property | Description
---|---
`password` | (required) password
`email_verification_code` | (required) verificaion code from email
`sms_verification_code` | (optional) verification code from sms (not implemented) 

#### Example response

```json
{
    "code": 200,
    "message": "Sign-up successfully "
}
```