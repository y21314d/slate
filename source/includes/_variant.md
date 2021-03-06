# Variant

## Variant List Without Login

### Description

| Title | Description |
| -------: | :---- |
| URL | `item/{item_id}/variant/list` |
| Method | `get` |
| Use | to get variant list |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "item_id": 1
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| item_id | integer | item’s id |

> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
    "variants": [
        {
            "id": 1,
            "name": "CB SBC26",
            "default_price": 10000,
            "stock": 10,
            "cover_image": {
				"name": "xxx.jpg",
				"cover": 1,
				"resource": {
					"px240": "http://abc/xxx_240p.jpg",
					"px480": "http://abc/xxx_480p.jpg",
					"px720": "http://abc/xxx_720p.jpg",
					"px1080": "http://abc/xxx_1080p.jpg"
                }
            },
            "images": [{
				"name": "xxx.jpg",
				"cover": 1,
				"resource": {
					"px240": "http://abc/xxx_240p.jpg",
					"px480": "http://abc/xxx_480p.jpg",
					"px720": "http://abc/xxx_720p.jpg",
					"px1080": "http://abc/xxx_1080p.jpg"
				}
			}, {
				"name": "yyy.jpg",
				"cover": 0,
				"resource": {
					"px240": "http://abc/yyy_240p.jpg",
					"px480": "http://abc/yyy_480p.jpg",
					"px720": "http://abc/yyy_720p.jpg",
					"px1080": "http://abc/yyy_1080p.jpg"
				}
			}]
        },
        {
            "id": 3,
            "name": "CB SBC22",
            "default_price": 9000,
            "stock": 5,
            "cover_image": {},
            "images":[{
				"name": "xxx.jpg",
				"cover": 1,
				"resource": {
					"px240": "http://abc/xxx_240p.jpg",
					"px480": "http://abc/xxx_480p.jpg",
					"px720": "http://abc/xxx_720p.jpg",
					"px1080": "http://abc/xxx_1080p.jpg"
				}
			}]
        },
        {
            "id": 4,
            "name": "CB SBC2254",
            "default_price": 3324,
            "stock": 0,
            "cover_image": {},
            "images": []
        },
        {
            "id": 5,
            "name": "CC SCR5543624",
            "default_price": 3624,
            "stock": 10,
            "cover_image": {},
            "images": [{
				"name": "xxx.jpg",
				"cover": 1,
				"resource": {
					"px240": "http://abc/xxx_240p.jpg",
					"px480": "http://abc/xxx_480p.jpg",
					"px720": "http://abc/xxx_720p.jpg",
					"px1080": "http://abc/xxx_1080p.jpg"
				}
			}, {
				"name": "yyy.jpg",
				"cover": 0,
				"resource": {
					"px240": "http://abc/yyy_240p.jpg",
					"px480": "http://abc/yyy_480p.jpg",
					"px720": "http://abc/yyy_720p.jpg",
					"px1080": "http://abc/yyy_1080p.jpg"
				}
			}]
        }
    ]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| **variants** | **array** | a set of variant object |
| id | integer |  variant’s id |
| name | string |  variant’s name |
| default_price | numeric | default price of variant |
| stock | numeric | stock of variant |
| **cover_img** | **object** | variant cover image. It will be empty if no set cover image |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| *resource* | **object** | cover image tag |
| *px240* | string | picture url of 240 resolution (426x240) |
| *px480* | string | picture url of 480 resolution (854x480) |
| *px720* | string | picture url of 720 resolution (1280x720) |
| *px1080* | string | picture url of 1080 resolution (1920x1080) |
| **images** | **object** | It will get variant images first.If there's no variant images it will get item images. It will be empty if no item and variant image |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| *resource* | **object** | cover image tag |
| *px240* | string | picture url of 240 resolution (426x240) |
| *px480* | string | picture url of 480 resolution (854x480) |
| *px720* | string | picture url of 720 resolution (1280x720) |
| *px1080* | string | picture url of 1080 resolution (1920x1080) |

<aside class="warning">
Failure
</aside>

```json
{
    "error_name":"lack of parameters"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | the name of the wrong type. |
||| **lack of parameters:** the request does not include the necessary parameters |
||| **item not exist:** currenct item not exist |

## Variant List

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/item/variant/list` |
| Method | `post` |
| Use | to get variant list |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "target_company_id": 1,
    "item_id": 1
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| target_company_id | integer | company id which user want get variant  list |
| item_id | integer | item’s id |

> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
    "variants": [{
        "variant_id": 1,
        "name": "Color",
        "number": "autark-k1-ss-001",
        "stock": 5,
        "default_price": 100,
        "default_deposit": 20,
        "company_id": 1,
        "cover_img": {
			"name": "xxx.jpg",
			"cover": true,
			"resource": {
				"240p": "http://abc/xxx_240p.jpg",
				"480p": "http://abc/xxx_480p.jpg",
				"720p": "http://abc/xxx_720p.jpg",
				"1080p": "http://abc/xxx_1080p.jpg"
			}
		}
    }]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| **variants** | **array** | a set of variant object |
| id | integer |  variant’s id |
| name | string |  variant’s name |
| number | string |  variant’s number |
| stock | integer | product number of variant |
| default_price | numeric | default price of variant |
| default_deposit | numeric | default deposit of variant |
| company_id | integer | variant belongs to which company |
| **cover_img** | **object** | variant cover image. It will be empty if no set cover image |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| *resource* | **object** | cover image tag |
| *240p* | string | picture url of 240 resolution (426x240) |
| *480p* | string | picture url of 480 resolution (854x480) |
| *720p* | string | picture url of 720 resolution (1280x720) |
| *1080p* | string | picture url of 1080 resolution (1920x1080) |

<aside class="warning">
Failure
</aside>

```json
{
    "error_name":"lack of parameters"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | the name of the wrong type. |
||| **lack of parameters:** the request does not include the necessary parameters |
||| **does not signin:** user does not signin |
||| **not select company yet:** user need change current company |
||| **company not exist:** currenct company not exist |
||| **not company member:** the user is not the company member |


## Create Variant

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/item/variant/create` |
| Method | `post` |
| Use | to create variant |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "item_id": 1,
    "name": "Basic",
    "number": "autark-k1-ss-001",
    "website": "",
    "taric_code": "",
    "prices": [{
        "currency_id": 1,
        "price": 100
    }],
    "customizations": [{
        "id": 1,
        "value": 2
    }, {
        "id": 3,
        "value": 10
    }],
    "images": [{
		"name": "asdasdasd.jpg",
		"cover": true
	}, {
		"name": "qweqweq.jpg",
		"cover": false
	}],
	"warranty": {
		"type": "Limited",
		"value": 2,
		"unit": "Years"
	}
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| item_id | integer | item’s id |
| name | string | variant’s name |
| number | string | variant’s number |
| website | string | variant’s website |
| taric_code | string | variant’s taric code |
| **prices** | **array** | variant’s prices in the each currency |
| *currency_id* | integer | currency  id |
| *price* | number |  price of corresponding currency |
| **customizations** | **array** | customization settings of variant |
| *id* | integer | customization’s id |
| *value* | integer | id of customization value |
| **images** | **array** | variant images |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| **warranty** | **object** | warranty setting of item |
| *type* | string | warranty type - Limited or Lifetime |
| *value* | positive integer (option) | warranty value |
| *unit* | string (option) | value unit - Years or Months |

> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| (Nothing return) | - | - |

<aside class="warning">
Failure
</aside>

```json
{
    "error_name":"lack of parameters"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | the name of the wrong type. |
||| **lack of parameters:** the request does not include the necessary parameters |
||| **does not signin:** user does not signin |
||| **not select company yet:** user need change current company |
||| **company not exist:** currenct company not exist |
||| **not company member:** the user is not the company member |
||| **illegal form input:** form format does not pass validation |
| **validation** | **object** | if the err_name is illegal form input', web backend should assign the name of the wrong type for each error input. **Value(option):** |
| *name* | array | **required:** it’s necessary column for this api |
| *customizations* | array | **required:** it’s necessary parameter |
||| **duplicate:**  this customization setting has been used |

## Variant  Detail Without Login

### Description

| Title | Description |
| -------: | :---- |
| URL | `variant/{variant_id}/detail` |
| Method | `get` |
| Use | to show variant  detail |
| Notice ||


> Input Parameters

### Input Parameters

```json
{
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
	"id": 1,
	"name": "CB SBC26",
    "item_name": "CB SBC",
    "default_price": 10000,
    "customizations": [
        {
            "id": 79,
            "name": "SIZE",
            "value": {
                "id": 274,
                "name": "SMALL"
            }
        },{
            "id": 80,
            "name": "COLOR",
            "value": {
                "id": 275,
                "name": "WHITE"
            }
        }],
    "images": [
        {
            "name": "xxx.jpg",
            "cover": 0,
            "resource": {
				"px240": "http://abc/xxx_240p.jpg",
				"px480": "http://abc/xxx_480p.jpg",
				"px720": "http://abc/xxx_720p.jpg",
				"px1080": "http://abc/xxx_1080p.jpg"
            }
        },
        {
            "name": "yyy.jpg",
            "cover": 1,
            "resource": {
				"px240": "http://abc/yyy_240p.jpg",
				"px480": "http://abc/yyy_480p.jpg",
				"px720": "http://abc/yyy_720p.jpg",
				"px1080": "http://abc/yyy_1080p.jpg"
            }
        }
    ]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | integer | variant’s  id |
| name | string | variant’s  name |
| item_name | string | item name of variant  |
| default_price | integer | variant default price |
| **customizations** | **array** | customizations setting of variant |
| *id* | integer | customization’s id |
| *name* | string | customization name |
| *display_name* | string | customization display name |
| *value* | **object** | customization value |
| *id* | integer |  id of customization value |
| *name* | string |  name of customization value |
| **images** | **array** | variant images |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| *resource* | **object** | cover image tag |
| *px240* | string | picture url of 240 resolution (426x240) |
| *px480* | string | picture url of 480 resolution (854x480) |
| *px720* | string | picture url of 720 resolution (1280x720) |
| *px1080* | string | picture url of 1080 resolution (1920x1080) |

<aside class="warning">
Failure
</aside>

```json
{
    "error_name":"variant not exist"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | the name of the wrong type. |
||| **variant not exist:** |

## Variant  Detail

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/item/variant/detail` |
| Method | `post` |
| Use | to show variant  detail |
| Notice ||


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "target_company_id": 1,
    "variant_id": 1
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| target_company_id | integer | company id which user want get variant list |
| variant_id | integer | variant’s  id |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
    "id": 1,
    "name": "Basic",
    "number": "autark-k1-ss-001",
    "website": "",
    "taric_code": "",
    "item": [{
        "id": 1,
        "number":"NoteBook-1",
        "name": "NoteBookl",
    "company_id":1
    }],
    "prices": {
        "EUR": 100,
        "TWD": 3300
    },
    "default_deposit": 20,
    "customizations": [{
        "id": 1,
        "name": "Backgroud Color",
        "display_name": "Color",
        "value": {
            "id": 1,
            "name": "Red"
        }
    }, {
        "id": 2,
        "name": "Color",
        "display_name": "Color",
        "value": {
            "id":2,
            "name": "Red"
        }
    }],
    "images":[{
		"name": "xxx.jpg",
		"cover": true,
		"resource": {
			"240p": "http://abc/xxx_240p.jpg",
			"480p": "http://abc/xxx_480p.jpg",
			"720p": "http://abc/xxx_720p.jpg",
			"1080p": "http://abc/xxx_1080p.jpg"
		}
	}, {
		"name": "yyy.jpg",
		"cover": false,
		"resource": {
			"240p": "http://abc/yyy_240p.jpg",
			"480p": "http://abc/yyy_480p.jpg",
			"720p": "http://abc/yyy_720p.jpg",
			"1080p": "http://abc/yyy_1080p.jpg"
		}
	}],
	"warranty": {
		"type": "Limited",
		"value": 2,
		"unit": "Years"
	}
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | integer | variant’s  id |
| name | string | variant’s  name |
| number | string | variant’s number |
| website | string | variant’s website |
| taric_code | string | variant’s taric code |
| **item** | **object** | item which variant belongs |
| *id* | integer | item’s id |
| *number* | string | item’s number |
| *name* | string | item’s name |
| **prices** | **object** | variant’s price in the each currency |
| *currency_name* | numeric | price of variant in this currency |
| default_deposit | numeric | default deposit of variant |
| **customizations** | **array** | customizations setting of variant |
| *id* | integer | customization’s id |
| *name* | string | customization name |
| *display_name* | string | customization display name |
| *value* | **object** | customization value |
| *id* | integer |  id of customization value |
| *name* | string |  name of customization value |
| **images** | **array** | variant images |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| *resource* | **object** | cover image tag |
| *240p* | string | picture url of 240 resolution (426x240) |
| *480p* | string | picture url of 480 resolution (854x480) |
| *720p* | string | picture url of 720 resolution (1280x720) |
| *1080p* | string | picture url of 1080 resolution (1920x1080) |
| **warranty** | **object** | warranty setting of variant |
| *type* | string | warranty type |
| *value* | integer | warranty value |
| *unit* | string | value unit |

<aside class="warning">
Failure
</aside>

```json
{
    "error_name":"lack of parameters"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | the name of the wrong type. |
||| **lack of parameters:** some input parameters missing, not in the request |
||| **does not signin:** user does not signin |
||| **not select company yet:** user need change current company |
||| **company not exist:** currenct company not exist |
||| **not company member:** the user is not the company member |
||| **variant not exist:** |


## Edit Variant

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/item/variant/edit` |
| Method | `post` |
| Use | to edit variant |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "variant_id": 1,
    "name": "Basic",
    "number": "autark-k1-ss-001",
    "website": "",
    "taric_code": "",
    "prices": [{
        "currency_id": 1,
        "price": 100
    }],
    "customizations": [{
        "id": 1,
        "value": 2
    }, {
        "id": 3 ,
        "value": 10
    }],
    "images": [{
		"name": "asdasdasd.jpg",
		"cover": true
	}, {
		"name": "qweqweq.jpg",
		"cover": false
	}],
	"warranty": {
		"type": "Limited",
		"value": 2,
		"unit": "Years"
	}
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| variant_id | integer |  item id |
| name | string | variant’s name |
| number | string | variant’s number |
| website | string | variant’s website |
| taric_code | string | variant’s taric code |
| **prices** | **array** |  variant’s prices in the each currency |
| *currency_id* | integer | currency id |
| *price* | numeric | price of corresponding currency |
| **customizations** | **array** | customization settings of variant |
| *id* | integer | customization’s id |
| *value* | integer |  id of customization value  |
| **images** | **array** | variant images |
| *name* | string | file name which get from back end after specific image has been updated |
| *cover* | boolean | cover image tag |
| **warranty** | **object** | warranty setting of item |
| *type* | string | warranty type - Limited or Lifetime |
| *value* | positive integer (option) | warranty value |
| *unit* | string (option) | value unit - Years or Months |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| (Nothing return) | - | - |


<aside class="warning">
Failure
</aside>

```json
{
    "error_name":""
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | the name of the wrong type. |
||| **lack of parameters:** some input parameters missing, not in the request |
||| **does not signin:** user does not signin |
||| **not company member:**  user are not member in this company |
||| **invalid customization:** customization is not include this value(value of vustomization error) |
||| **illegal form input:** validate unsuccess, the exact error message will in validation of data |
| **validation** | **object** | if the err_name is illegal form input', web backend should assign the name of the wrong type for each error input. **Value(option):**|
| *name* | array | **required:** it’s necessary column for this api |
|||**dulicate:** the name has already been taken|
| *price* | array | **required:** it’s necessary column for this api |
| *customizations* | array | **required:**  it’s necessary column for this api |
|||**dulicate:**  this customization style has been used|
