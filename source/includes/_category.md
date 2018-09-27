# Category

## Category List Without Login

### Description

| Title | Description |
| -------: | :---- |
| URL | `company/{company_id}/category/list` | 
| Method | `get` | 
| Use | to get company category |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"company_id": 1
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| company_id | integer | company id which user want get category list |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
	"id": 1,
	"name": "Root",
	"subCategories": [{
		"id": 2,
		"name": "Category Test",
		"subCategories": [],
	}],
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | integer | category id |
| name | string | category name |
| id | integer | item id |
| name | string | item name |
| subCategories | **object** | property same as above |

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
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**company not exist:** currenct company not exist|

## Category List

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/category/list` | 
| Method | `post` | 
| Use | to get company category |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"api_key": "e4cbcdc2faff41a7e311",
	"target_company_id": 1
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| target_company_id | integer | company id which user want get category list |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
	"id": 1,
	"name": "Root",
	"subCategory": [{
		"id": 2,
		"name": "Category Test",
		"subCategory": [],
		"items": []
	}],
	"items": [{
		"id": 1,
		"number": "item number",
		"name": "item name",
		"cover_img": {
			"240p": "asdsad_240p.jpeg",
			"480p": "asdsad_480p.jpeg",
			"720p": "asdsad_720p.jpeg",
			"1080p": "asdsad_1080p.jpeg"
		}
	}]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | integer | category id |
| name | string | category name |
| **items** | **array** | items belong to current category |
| id | integer | item id |
| number | string | item number |
| name | string | item name |
| cover_img | **object** | item cover image. It will be empty if no set cover image |
| *240p* | string | picture url of 240 resolution (426x240) |
| *480p* | string | picture url of 480 resolution (854x480) |
| *720p* | string | picture url of 720 resolution (1280x720) |
| *1080p* | string | picture url of 1080 resolution (1920x1080) |
| subCategory | **object** | property same as above |

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
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**does not signin:** user does not signin|
|||**not select company yet:** user need change current company|
|||**company not exist:** currenct company not exist|
|||**not company member:** the user is not the company member|


## Create Category

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/category/create` | 
| Method | `post` | 
| Use | to create category |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"api_key": "e4cbcdc2faff41a7e311",
	"name": "category name",
	"description": "",
	"parent_id": 1,
	"specs": [1, 2, 3],
	"customizations": [1, 2, 3]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| name | string | category name |
| description | string | category description |
| parent_id | integer | who is category parent |
| specs | array | spec id set |
| customizations | array | customization id set |



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
	"validation": {
		"name": ["dulicate"],
		"parent_id": ["required"]
	},
	"error_name": "illegal form input"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**does not signin:** user does not signin|
|||**not select company yet:** user need change current company|
|||**company not exist:** currenct company not exist|
|||**not company member:** the user is not the company member|
|||**illegal form input:** form format does not pass validation|
| **validation** | **object** | if the err_name is illegal form input', web backend should assign the name of the wrong type for each error input. **Value(option):**|
| name | array | **required:** it’s necessary parameter |
| parent_id | array | **required:** it’s necessary parameter 
|||**not exist:** category id not exist|

## Category Item List Without Login

### Description

| Title | Description |
| -------: | :---- |
| URL | `category/{category_id}/item/list` | 
| Method | `get` | 
| Use | to show category item list |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"category_id": 1,
	"page": 1,
	"perpage": 2
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| category_id | integer | category id |
| page | integer(option) | the page of all items list, page < 0 will set to first page, page > last page will set to last page, default: 1 |
| perpage | integer(option) | items per page, default: 60 |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
	"id": 1,
	"name": "Category Name",
	"items":[{
		"id": 1,
		"name": "Edison Evo",
		"cover_img": {
			"px240": "http://abc/xxx_240p.jpg",
			"px480": "http://abc/xxx_480p.jpg",
			"px720": "http://abc/xxx_720p.jpg",
			"px1080": "http://abc/xxx_1080p.jpg"
		},
        "currency": "EUR",
        "price": 10
	}],
	"pager": {	
        "total": 31,
		"per_page": 2,
		"current_page": 1,
		"last_page": 16
    }
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | integer | category id |
| name | string | category name |
| **items** | **array** | items in this category |
| *id* | integer | item id |
| *name* | string | item name |
| *price* | number | item price |
| *currency* | string | default currency name of company |
| *cover_img* | **object** | item cover image. It will be empty if no set cover image |
| *px240* | string | picture url of 240 resolution (426x240) |
| *px480* | string | picture url of 480 resolution (854x480) |
| *px720* | string | picture url of 720 resolution (1280x720) |
| *px1080* | string | picture url of 1080 resolution (1920x1080) |
| **pager** | **object** | items pager |
| *total* | integer | total number of data records |
| *per_page* | integer | items per page for input |
| *current_page* | integer | current page number |
| *last_page* | integer | last page number |


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
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**company not exist:** currenct company not exist|
|||**category not exist:** category id is incorrect|
|||**illegal form input':** form format does not pass validation|

## Category Detail

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/category/detail` | 
| Method | `post` | 
| Use | to show category list, not include categories and items in sub-catgory |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"api_key": "e4cbcdc2faff41a7e311",
	"target_company_id": 1,
	"category_id": 1,
	"pager": true,
	"page": 1,
	"perpage": 2
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| target_company_id | integer | company id which user want get category detail |
| category_id | integer | category id |
| pager | string/boolean(option) | the flag of all items pager(true/false, default:false) |
| page | integer(option) | the page of all items list, page < 0 will set to first page, page > last page will set to last page |
| perpage | integer(option) | items per page |


> Return Parameters

### Return Parameters

<aside class="success">
Success
</aside>

```json
{
	"id": 1,
	"name": "Category Name",
	"description": "",
	"parent": {
		"id": "",
		"name": "",
		"specs": [],
		"customizations": []
	},
	"specs": [{
		"id": 1,
		"name": "Spec Name"
	}],
	"customizations": [{
		"id": 1,
		"name": "Customization  Name"
	}],
	"subCategory":[{
		"id":"1",
		"name":"Mountain Bike"
	},{
		"id":"2",
		"name":"Road Bike"
	}],
	"all_items": [],
	"items":[{
		"id": 1,
		"number": "item-1",
		"name": "Edison Evo",
		"company_id": 1,
		"cover_img": {
			"240p": "http://abc/xxx_240p.jpg",
			"480p": "http://abc/xxx_480p.jpg",
			"720p": "http://abc/xxx_720p.jpg",
			"1080p": "http://abc/xxx_1080p.jpg"
		}
	},{
		"id": 2,
		"number": "item-2",
		"name": "Cargo",
		"company_id": 1,
		"cover_img": {}
	}],
	"all_items_pager": {	
        "total": 31,
		"per_page": 2,
		"current_page": 1,
		"last_page": 16
    }
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| id | integer | category id |
| name | string | category name |
| description | string | category description |
| **parent** | **object** | parent category |
| *id* | integer | id of parent category |
| *name* | string | name of parent category |
| *specs* | array | parent own specs include parent’s parent… content same to specs |
| *customizations* | array | parent own customizations include parent’s parent… content same to customizations |
| **specs** | **array** | specs connect with category |
| *id* | integer | spec id |
| *name* | string | spec name |
| *display_name* | string | spec display name |
| *value* | **array** | spec values |
| *id* | integer | spec value id |
| *name* | string | spec value name |
| **customizations** | **array** | customizations connect with category |
| *id* | integer | customization id |
| *name* | string | customization name |
| *display_name* | string | customization display name |
| **subCategory** | **array** | sub categories |
| *id* | integer | subCategory id |
| *name* | string | subCategory name |
| **all_items** | **array** | items belongs to this category or subcategory |
| **items** | **array** | items in this category |
| *id* | integer | item id |
| *name* | string | item name |
| *number* | string | item number |
| *price* | number | item price |
| *currency* | string | default currency name of company |
| *company_id* | integer | company id of item |
| *cover_img* | **object** | item cover image. It will be empty if no set cover image |
| *240p* | string | picture url of 240 resolution (426x240) |
| *480p* | string | picture url of 480 resolution (854x480) |
| *720p* | string | picture url of 720 resolution (1280x720) |
| *1080p* | string | picture url of 1080 resolution (1920x1080) |
| **all_items_pager** | **object** | all_items pager |
| *total* | integer | total number of data records |
| *per_page* | integer | items per page for input |
| *current_page* | integer | current page number |
| *last_page* | integer | last page number |


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
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**does not signin:** user does not signin|
|||**not select company yet:** user need change current company|
|||**company not exist:** currenct company not exist|
|||**not company member:** the user is not the company member|
|||**category not exist:** category id is incorrect|
|||**illegal form input':** form format does not pass validation|



## Edit Category

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/category/edit` | 
| Method | `post` | 
| Use | to edit category |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"api_key": "e4cbcdc2faff41a7e311",
	"category_id": 1,
	"name": "category name",
	"description": "",
	"parent_id": 1,
	"specs": [1, 2, 3],
	"customizations": [1, 2, 3]
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| category_id | integer | category id |
| name | string | category name |
| description | string | category description |
| parent_id | integer | category location |
| specs | array | spec id set |
| customizations | array | customization id set |


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
	"validation": {
		"name": ["dulicate"],
		"parent_id": ["required"]
	},
	"error_name": "illegal form input"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**does not signin:** user does not signin|
|||**not select company yet:** user need change current company|
|||**company not exist:** currenct company not exist|
|||**not company member:** the user is not the company member|
|||**category not exist:** category id is incorrect|
|||**illegal form input:** form format does not pass validation|
| **validation** | **object** | if the err_name is illegal form input', web backend should assign the name of the wrong type for each error input. **Value(option):**|
| name | array | **required:** it’s necessary parameter |
| parent_id | array | **required:** it’s necessary parameter 
|||**not exist:** category id not exist|




## Delete Category

### Description

| Title | Description |
| -------: | :---- |
| URL | `user/company/category/delete` | 
| Method | `post` | 
| Use | to delete category |
| Notice |  |


> Input Parameters

### Input Parameters

```json
{
	"api_key": "e4cbcdc2faff41a7e311",
	"category_id": 1
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| api_key | string | Web backend gives user a unique token after user login in app, then user should use this token to request data from web backend. |
| category_id | integer | category id |


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
	"error_name": "lack of parameters"
}
```

| Parameter | Type | Description |
| -------: | :---- | :--- |
| error_name | String |  if the value of success is false, web backend needs to assign the name of  error, unless this parameter should be empty: Valid Value:| 
|||**lack of parameters:** some input parameters missing, not in the request|
|||**does not signin:** user does not signin|
|||**not select company yet:** user need change current company|
|||**company not exist:** currenct company not exist|
|||**not company member:** the user is not the company member|
|||**category not exist:** category id is incorrect|
