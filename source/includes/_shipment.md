# Shipment

## Shipment List

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/shipment/list` |
| Method | `post` |
| Use | show shipment list |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | The key will be returned by Sign In API |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
    "shipments_of_brand": [{
        "number": "AAAA0000000001SH",
        "status": "Preparing",
        "shipped_at": 1498730137,
        "comment": "",
        "shipped_area": {
            "id": 1,
            "name": "Aruba"
        },
        "company": {
            "id": 1,
            "name": "Bike"
        },
        "importer": {
            "id": 1,
            "name": "Bike"
        },
        "recipient": {
            "company_name": "Bike",
            "given_name": "Abc",
            "family_name": "Hi"
        }
    }],
    "shipments_of_importer": []
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| shipments_of_brand | array | the shipment is created by self |
| shipments_of_importer | array | the shipment is assigned to self |

| shipment | Type | Description |
| -------: | :---- | :--- |
| number | string | shipment latest status |
| status | string | shipment latest status |
| shipped_at | timestamp | shipped date |
| comment | string | shipment comment |
| shipped_area | object | country of shipped area |
| company | object | shipment creator |
| importer | object | company of importer |
| recipient | object | recipient information |

| shipped_area | Type | Description |
| -------: | :---- | :--- |
| id | integer | country id |
| name | name | country name |

| company | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id |
| name | name | company name |

| importer | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id of importer |
| name | name | company name of importer |

| recipient | Type | Description |
| -------: | :---- | :--- |
| company_name | string | the company which recipient belongs to |
| given_name | string | recipient given name |
| family_name | string | recipient family name |

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
| error_name | string | The name of wrong type <br/><ul><li>lack of parameters: the request does not include the necessary parameters</li><li>does not signin: user does not signin</li><li>not select company yet: user need change current company</li><li>company not exist: currenct company not exist</li><li>not company member: the user is not the company member</li></ul> |


## Shipment Detail

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/shipment/detail` |
| Method | `post` |
| Use | show shipment detail |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "shipment_number": "AAAA0000000001SH"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | The key will be returned by Sign In API |
| shipment_number | string | shipment number |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
	"id": 123,
    "number": "AAAA0000000001SH",
    "status": "Preparing",
    "proforma_invoice_number": "",
    "comment": "",
    "shipped_at": 1498730137,
    "tracking_number": "",
    "pieces": 1,
    "shipped_area": {
        "id": 1,
        "name": "Aruba"
    },
    "company": {
        "id": 1,
        "name": "Bike",
        "currency_name": "EUR"
    },
    "importer": {
        "id": 1,
        "name": "Bike",
        "given_name": "Abc",
        "family_name": "Hi",
        "title": 1,
        "phone": "0123456789",
        "email": "abc@abc.com",
        "street": "qq",
        "city": "ww",
        "state": "ee",
        "postal_code": "123",
        "country": "Taiwan"
    },
    "recipient": {
        "company_name": "Bike",
        "given_name": "Abc",
        "family_name": "Hi",
        "title": 1,
        "phone": "0123456789",
        "email": "abc@abc.com",
        "street": "qq",
        "city": "ww",
        "state": "ee",
        "postal_code": "123",
        "country": "Taiwan"
    },
    "histories": [{
        "id": 1,
        "status": "Preparing",
        "comment": "",
        "date": 1498730137
    }],
    "abnormal": false,
    "packages": [{
        "id": 1,
        "proforma_description": "",
        "invoice_show": true,
        "unit_value": 999.99,
        "item": {
            "id": 1,
            "name": "watch",
            "number": "watch-001"
        },
        "variant": {
            "id": 1,
            "name": "k1-gold",
            "taric_code": ""
        },
        "products": [{
        	"number": "AAAA0000000001PD",
			"serial_number": "aaaaa",
			"purchase_order_number": "AAAA010120160000PO",
			"abnormal": false,
			"sold": true
        }]
    }],
    "files": [{
        "id": 1,
        "name": "proforma.jpg",
        "date": 1498730137,
        "comment": "proforma invoice",
        "uploaded_by": {
            "id": 1,
            "given_name": "Abc",
            "family_name": "Hi",
            "company": {
                "id": 1,
                "name": "Bike"
            }
        },
        "download": "http:abc.abc.com"
    }],
    "status_message": {
        "country": "country not found",
        "importer": "importer not in country"
    }
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | string | shipment id |
| number | string | shipment number |
| proforma_invoice_number | string | proforma invoice number of shipment |
| status | string | shipment latest status |
| comment | string | shipment comment |
| shipped_at | timestamp | shipped date |
| tracking_number | string | tracking number of logistics company |
| pieces | integer | total unit of shipment |
| shipped_area | object | country of shipped area |
| company | object | the company of creating shipment |
| importer | object | the importer company |
| recipient | object | recipient information |
| histories | array | shipment status |
| abnormal | boolean | it's true mean shipment include below problem <ol><li>There are duplicate spec combination of variant as package</li><li>The spec combination of product is not match package</li></ol> |
| packages | array | shipment packages |
| files | array | relative files of shipment |
| status_message | object | the hint to tell user this shipment is not complete |

| shipped_area | Type | Description |
| -------: | :---- | :--- |
| id | integer | country id |
| name | name | country name |

| company | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id |
| name | name | company name |
| currency_name | string | default currency of company |

| importer | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id of importer |
| name | name | company name of importer |
| given_name | string | given_name of contact person of importer |
| family_name | string | family_name of contact person of importer |
| title | string | title of contact person of importer |
| phone | string | phone of contact person of importer |
| email | string | email of contact person of importer |
| street | string | importer street |
| city | string | importer city |
| state | string | importer state |
| postal_code | string | importer postal_code |
| country | string | importer country |

| recipient | Type | Description |
| -------: | :---- | :--- |
| company_name | string | the company of recipient |
| given_name | string | recipient given_name |
| family_name | string | recipient family_name |
| title | string | recipient title |
| phone | string | recipient phone |
| email | string | recipient email |
| street | string | recipient street |
| city | string | recipient city |
| state | string | recipient state |
| postal_code | string | recipient postal_code |
| country | string | recipient country |

| histories | Type | Description |
| -------: | :---- | :--- |
| id | string | history city |
| status | string | history status |
| comment | string | history comment |
| date | timestamp | history created date |

| packages | Type | Description |
| -------: | :---- | :--- |
| id | integer | package id |
| proforma_description | string | proforma description |
| invoice_show | boolean | show product number in the proforma invoice |
| unit_value | double | unit value of item |
| item | object | item information of package |
| variant | object | variant information of package |
| products | array | a set of product number in the package |

| packages.item | Type | Description |
| -------: | :---- | :--- |
| id | integer | item id |
| name | string | item name |
| number | string | item number |

| packages.variant | Type | Description |
| -------: | :---- | :--- |
| id | integer | variant id |
| name | string | variant name |
| taric_code | string | variant taric code |

| packages.products | Type | Description |
| -------: | :---- | :--- |
| number | string | The number of product |
| serial_number | string | The serial number of product |
| sold | boolean | The status of product<ol><li>true: sold</li><li>false: unsold</li></ol> |
| purchase_order_number | string | The purchase order number which product is assigned<br />It's null when product is not assigned to purchase order |
| abnormal | boolean | it's true mean the spec combination of product is not match package |


| files | Type | Description |
| -------: | :---- | :--- |
| id | integer | file id |
| name | string | file name |
| date | timestamp | uploaded date |
| comment | string | file comment |
| uploaded_by | object | uploaded information |
| download | string | download link, need include Authorization header in the request |

| files.uploaded_by | Type | Description |
| -------: | :---- | :--- |
| id | integer | user id |
| given_name | string | given name of user |
| family_name | string | family name of user |
| company | object | uploaded company information |

| files.uploaded_by.company | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id |
| name | string | company name |

<aside class="warning">
Failure
</aside>

```json
{
    "error_name":"does not signin"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | The name of wrong type <br/><ul><li>lack of parameters: the request does not include the necessary parameters</li><li>does not signin: user does not signin</li><li>not select company yet: user need change current company</li><li>company not exist: currenct company not exist</li><li>not company member: the user is not the company member</li><li>shipment not found: shipment not exist</li><li>permission denied: Just the company of creating shipment or importer can get detail</li></ul> |


## Create Shipment

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/shipment/create` |
| Method | `post` |
| Use | create shipment |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "proforma_invoice_number": "",
    "comment": "",
    "shipped_at": {
        "timestamp": 1498730137,
        "offset": 28800
    },
    "tracking_number": "",
    "pieces": 1,
    "shipped_area_id": 1,
    "importer": {
        "id": 1,
        "given_name": "Abc",
        "family_name": "Hi",
        "title": 1,
        "phone": "0123456789",
        "email": "abc@abc.com",
        "street": "qq",
        "city": "ww",
        "state": "ee",
        "postal_code": "123",
        "country": "Taiwan"
    },
    "recipient": {
        "company_name": "Bike",
        "given_name": "Abc",
        "family_name": "Hi",
        "title": 1,
        "phone": "0123456789",
        "email": "abc@abc.com",
        "street": "qq",
        "city": "ww",
        "state": "ee",
        "postal_code": "123",
        "country": "Taiwan"
    },
    "added_histories": [{
        "status": "Preparing",
        "comment": "",
        "date": 1498730137
    }],
    "added_packages": [{
        "variant_id": 1,
        "proforma_description": "",
        "invoice_show": true,
        "products": ["AAAA0000000001PD", "AAAA0000000011PD"],
        "unit_value": 999.99
    }],
    "added_files": [{
        "name": "proforma.jpg",
        "date": 1498730137,
        "comment": "proforma invoice",
        "resource": ""
    }]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | The key will be returned by Sign In API |
| proforma_invoice_number | string (option) | proforma_invoice_number of shipment |
| comment | string (option) | shipment comment |
| shipped_at | object (option) | shipped date |
| tracking_number | string | tracking number of logistics company |
| pieces | integer (option) | total unit of shipment |
| shipped_area_id | integer (option) | country id of shipped area <br/> the shipped_area_id is required if the importer exist |
| importer | object (option) | importer information |
| recipient | object (option) | recipient information |
| added_histories | array (option) | added histories |
| added_packages | array (option) | added packages |
| added_files | array (option) | uploaded files |

| shipped_at | Type | Description |
| -------: | :---- | :--- |
| timestamp | timestamp | specifies the desired time as seconds since midnight, January 1, 1970 UTC |
| offset | integer | the offset from UTC (in seconds) for the current area |

| importer | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id of importer in shipped country |
| given_name | string | given_name of contact person of importer |
| family_name | string | family_name of contact person of importer |
| title | string | title of contact person of importer |
| phone | string | phone of contact person of importer |
| email | string | email of contact person of importer |
| street | string | importer street |
| city | string | importer city |
| state | string | importer state |
| postal_code | string | importer postal_code |
| country | string | importer country |

| recipient | Type | Description |
| -------: | :---- | :--- |
| company_name | string | the company which recipient belongs to |
| given_name | string | recipient given_name |
| family_name | string | recipient family_name |
| title | string | recipient title |
| phone | string | recipient phone |
| email | string | recipient email |
| street | string | recipient street |
| city | string | recipient city |
| state | string | recipient state |
| postal_code | string | recipient postal_code |
| country | string | recipient country |

| added_histories | Type | Description |
| -------: | :---- | :--- |
| status | string | history status <ul><li>(empty)</li><li>Preparing</li><li>Prepared</li><li>On Route</li><li>Complete</li><li>Returned</li></ul> |
| comment | string | history comment |
| date | string | history created date |

| added_packages | Type | Description |
| -------: | :---- | :--- |
| variant_id | integer | variant id of package |
| proforma_description | string | proforma description |
| invoice_show | boolean | show product number in the proforma invoice |
| unit_value | double | unit value of item |
| products | array | a set of product number in the package |

| added_files | Type | Description |
| -------: | :---- | :--- |
| name | string | file name |
| date | timestamp | uploaded date |
| comment | string | file comment |
| resource | string | uploaded data which is encrypted by base64, exclude mime type |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>


The return same to Get Purchase Order Detail API


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
| error_name | string | The name of wrong type <br/><ul><li>lack of parameters: the request does not include the necessary parameters</li><li>does not signin: user does not signin</li><li>not select company yet: user need change current company</li><li>company not exist: currenct company not exist</li><li>not company member: the user is not the company member</li><li>shipment not found: shipment not exist</li><li>illegal_form_input: The form format does not pass validation</li></ul> |
| validation | object (option) | if the err_name is 'illegal_form_input', system should assign the name of wrong type for each error input |
| invalid_products | array (option) | invalid products |
| conflict_products | array (option) | conflict products |
| sold_products | array (option) | sold products |

| validation | Type | Description |
| -------: | :---- | :--- |
| country | array (option) | <ul><li>country not found: shipped_area_id is invalid</li></ul> |
| importer | array (option) | <ul><li>shipped_area_id is required: </li><li>importer not in country: </li></ul> |
| added_histories | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invlid status: invalid status</li><li>invlid date format: date not timestamp</li></ul> |
| added_packages | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invalid variant: variant not found</li><li>invalid products: product not belongs to variant</li><li>conflict products: product has already been assigned</li><li>sold products: product has already sold</li></ul> |
| added_files | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invlid date format: date not timestamp</li></ul> |

| products | Type | Description |
| -------: | :---- | :--- |
| products | array | a set of product number |
| variant | object | variant of product |

| products.variant | Type | Description |
| -------: | :---- | :--- |
| id | integer | variant id |
| name | string | variant name |


## Edit Shipment

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/shipment/edit` |
| Method | `post` |
| Use | edit shipment |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "shipment_number": "AAAA0000000001SH",
    "proforma_invoice_number": "",
    "comment": "",
    "shipped_at": {
        "timestamp": 1498730137,
        "offset": 28800
    },
    "tracking_number": "",
    "pieces": 1,
    "shipped_area_id": 1,
    "importer": {
        "id": 1,
        "given_name": "Abc",
        "family_name": "Hi",
        "title": 1,
        "phone": "0123456789",
        "email": "abc@abc.com",
        "street": "qq",
        "city": "ww",
        "state": "ee",
        "postal_code": "123",
        "country": "Taiwan"
    },
    "recipient": {
        "company_name": "Bike",
        "given_name": "Abc",
        "family_name": "Hi",
        "title": 1,
        "phone": "0123456789",
        "email": "abc@abc.com",
        "street": "qq",
        "city": "ww",
        "state": "ee",
        "postal_code": "123",
        "country": "Taiwan"
    },
    "added_histories": [],
    "added_packages": [],
    "added_files": [],
    "edited_histories": [{
        "id": 1,
        "comment": ""
    }],
    "edited_packages": [{
        "id": 1,
        "proforma_description": "",
        "invoice_show": true,
        "products": ["AAAA0000000001PD", "AAAA0000000011PD"],
        "unit_value": 999.99
    }],
    "deleted_histories": [1, 2, 3],
    "deleted_packages": [1, 2, 3],
    "deleted_files": [1, 2, 3]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | The key will be returned by Sign In API |
| shipment_number | string | shipment number |
| proforma_invoice_number | string (option) | proforma_invoice_number of shipment |
| comment | string (option) | shipment comment |
| shipped_at | object (option) | shipped date |
| tracking_number | string | tracking number of logistics company |
| pieces | integer (option) | total unit of shipment |
| shipped_area_id | integer (option) | country id of shipped area <br/> the shipped_area_id is required if the importer exist |
| importer | object (option) | importer information |
| recipient | object (option) | recipient information |
| added_histories | array (option) | added histories |
| added_packages | array (option) | added packages |
| added_files | array (option) | uploaded files |
| edited_histories | array (option) | edited histories |
| edited_packages | array (option) | edited packages |
| deleted_histories | array (option) | a set of historie id |
| deleted_packages | array (option) | a set of package id |
| deleted_files | array (option) | a set of file id |

| shipped_at | Type | Description |
| -------: | :---- | :--- |
| timestamp | timestamp | specifies the desired time as seconds since midnight, January 1, 1970 UTC |
| offset | integer | the offset from UTC (in seconds) for the current area |

| importer | Type | Description |
| -------: | :---- | :--- |
| id | integer | company id of importer in shipped country |
| given_name | string | given_name of contact person of importer |
| family_name | string | family_name of contact person of importer |
| title | string | title of contact person of importer |
| phone | string | phone of contact person of importer |
| email | string | email of contact person of importer |
| street | string | importer street |
| city | string | importer city |
| state | string | importer state |
| postal_code | string | importer postal_code |
| country | string | importer country |

| recipient | Type | Description |
| -------: | :---- | :--- |
| company_name | string | the company which recipient belongs to |
| given_name | string | recipient given_name |
| family_name | string | recipient family_name |
| title | string | recipient title |
| phone | string | recipient phone |
| email | string | recipient email |
| street | string | recipient street |
| city | string | recipient city |
| state | string | recipient state |
| postal_code | string | recipient postal_code |
| country | string | recipient country |

| added_histories | Type | Description |
| -------: | :---- | :--- |
| status | string | history status <ul><li>(empty)</li><li>Preparing</li><li>Prepared</li><li>On Route</li><li>Complete</li><li>Returned</li></ul> |
| comment | string | history comment |
| date | string | history created date |

| added_packages | Type | Description |
| -------: | :---- | :--- |
| variant_id | integer | variant id of package |
| proforma_description | string | proforma description |
| invoice_show | boolean | show product number in the proforma invoice |
| unit_value | double | unit value of item |
| products | array | a set of product number in the package |

| added_files | Type | Description |
| -------: | :---- | :--- |
| name | string | file name |
| date | timestamp | uploaded date |
| comment | string | file comment |
| resource | string | uploaded data which is encrypted by base64, exclude mime type |

| edited_histories | Type | Description |
| -------: | :---- | :--- |
| id | integer | history id |
| comment | string | history comment |

| edited_packages | Type | Description |
| id | integer | package id |
| proforma_description | string | proforma description |
| invoice_show | boolean | show product number in the proforma invoice |
| unit_value | double | unit value of item |
| products | array | a set of product number in the package |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>


The return same to Get Purchase Order Detail API


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
| error_name | string | The name of wrong type <br/><ul><li>lack of parameters: the request does not include the necessary parameters</li><li>does not signin: user does not signin</li><li>not select company yet: user need change current company</li><li>company not exist: currenct company not exist</li><li>not company member: the user is not the company member</li><li>shipment not found: shipment not exist</li><li>illegal_form_input: The form format does not pass validation</li></ul> |
| validation | object (option) | if the err_name is 'illegal_form_input', system should assign the name of wrong type for each error input |
| invalid_products | array (option) | invalid products |
| conflict_products | array (option) | conflict products |
| sold_products | array (option) | sold products |

| validation | Type | Description |
| -------: | :---- | :--- |
| country | array (option) | <ul><li>country not found: shipped_area_id is invalid</li></ul> |
| importer | array (option) | <ul><li>shipped_area_id is required: </li><li>importer not in country: </li></ul> |
| added_histories | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invlid status: invalid status</li><li>invlid date format: date not timestamp</li></ul> |
| added_packages | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invalid variant: variant not found</li><li>invalid products product not belongs to variant</li><li>conflict products: product has already been assigned</li><li>sold products: product has already sold</li></ul> |
| added_files | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invlid date format: date not timestamp</li></ul> |
| edited_histories | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invalid histories: history id not found</li></ul> |
| edited_packages | array (option) | <ul><li>invalid format: required parameter not exist</li><li>invalid packages: package id not found</li><li>invalid products: product not belongs to variant</li><li>conflict products: product has already been assigned</li><li>sold products: product has already sold</li></ul> |
| deleted_histories | array (option) | <ul><li>invalid histories: history id not found</li></ul> |
| deleted_packages | array (option) | <ul><li>invalid packages: package id not found</li><li>sold products: product has already sold</li></ul> |
| deleted_files | array (option) | <ul><li>invalid files: file id not found</li></ul> |

| products | Type | Description |
| -------: | :---- | :--- |
| products | array | a set of product number |
| variant | object | variant of product |

| products.variant | Type | Description |
| -------: | :---- | :--- |
| id | integer | variant id |
| name | string | variant name |


## Delete Shipment

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/shipment/delete` |
| Method | `post` |
| Use | delete shipment |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
    "api_key": "e4cbcdc2faff41a7e311",
    "shipment_number": "AAAA0000000001SH"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | The key will be returned by Sign In API |
| shipment_number | string | shipment number |


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


<aside class="warning">
Failure
</aside>

```json
{
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | string | The name of wrong type <br/><ul><li>lack of parameters: the request does not include the necessary parameters</li><li>does not signin: user does not signin</li><li>not select company yet: user need change current company</li><li>company not exist: currenct company not exist</li><li>not company member: the user is not the company member</li><li>shipment not found: shipment not exist</li><li>permission denied: not shipment owner</li><li>sold products: products which assigned to shipment has be sold</li></ul> |


## Get Profoma Invoice PDF

### Description

| Title | Description |
| -------: | :---- |
| URL | `shipment/{shipment_number}/invoice/download` |
| Method | `get` |
| Use | get Profoma Invoice pdf |
| Notice |  |


> Header Parameters

### Header Parameters

```json
{
    "Authorization": "e4cbcdc2faff41a7e311"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| Authorization | string | The key will be returned by Sign In API |


> Input Parameters

### Input Parameters

| Parameter | Type | Description |
| -------: | :---- | :--- |
| shipment_number | string | shipment number |


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


<aside class="warning">
Failure
</aside>

```json
{
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |