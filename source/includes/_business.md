# Business

## Create Category

This API is used for create the Business category.

```shell
 curl -X POST \
 http://baseurl/api/location \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "categories": {
         "name": "Entertainment",
         "icon": "entertainment.png"
             }
}'
```

> The above command returns JSON structured like this:

```json
{
	"categories": {
		"id": "1",
		"name": "Entertainment",
		"icon": "entertainment.png"
	}
}


```


###HTTP Request

`POST http://base_url/api/category`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
name      | string| Name of the category |          
icon     | image | Image of the category| 


##Business Category List

This API is used for list of the Business category.

```shell
 curl -X GET \
 http://base_url/api/categories \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
  }'

```

> The above command returns JSON structured like this:

```json
{
	"categories": [{
		"id": "1",
		"name": "Entertainment",
		"icon": "entertainment.png"
	}, {
		"id": "2",
		"name": "Event",
		"icon": "event.png"
	}]
}
```


###HTTP Request

`GET http://base_url/api/categories`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
        |       |            |  


##Create Sub-Category

This API is used for create the Business sub category.

```shell
 curl -X POST \
 http://base_url/api/subcategory \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
      "sub_categories": {
      "name": "Boutiques",
      "icon": "boutiques.png"
        }
  }'



```

> The above command returns JSON structured like this:

```json
{
	"sub_categories": {
			"id": "1",
			"category_id": "1",
			"name": "Boutiques",
			"icon": "boutiques.png"
		}
}

```


###HTTP Request

`POST http://base_url/api/subcategory`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
name      |string| Name of the sub-category|          
category | integer| Id of the category  |
icon     | image | Image of the category| 

## Business Sub-Category List

This API is used for the sub category of the business.

```shell
 curl -X GET \
 http://base_url/api/category/:id/subcategories \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    }'
```

> The above command returns JSON structured like this:

```json
{
	"sub_categories": [{
			"id": "1",
			"category_id": "1",
			"name": "Boutiques",
			"icon": "boutiques.png"
		},
		{
			"id": "1",
			"category_id": "1",
			"name": "Groceries",
			"icon": "groceries.png"
		}
	]
}

```


###HTTP Request

`GET http://base_url/api/category/:id/subcategories`

### URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
        |       |            |  



## Create Business

This API is used for the create a Business.

```shell
 curl -X POST \
 http://base_url/api/business \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "business": {
        "name": "Pizza Plaza",
        "description": "Good shop",
        "category": "1",
        "subcategory": "1",
        "tag_line": "xyz",
        "offers": "10% discount",
        "image": "plaza.png",
        "phone": "9999999999",
        "website": "plaza.com",
        "address": "street 2,Big mall",
        "city": "Sacamento",
        "state": "California",
        "zip": "94203"
    }
}'
```

> The above command returns JSON structured like this:

```json
{
	"business": {
		"id": "1",
		"name": "Pizza Plaza",
		"description": "Good shop",
		"category": "1",
		"subcategory": "1",
		"tag_line": "xyz",
		"offers": "10% discount",
		"image": "plaza.png",
		"phone": "9999999999",
		"website": "plaza.com",
		"address": "street 2,Big mall",
		"city": "Sacamento",
		"state": "California",
		"zip": "94203"
	}
}
```


###HTTP Request

`POST http://base_url/api/business`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
name      | string | Name of the business |
description| string | Description of the business |
category  | string | Category of the business |
subcategory | string | Subcategory of the business |
tag_line   | string| Tag line of the business |
offers    | string | Offer of the business  |
image     |  image  |Image of the business |
phone     | string | Phone number of the buiness|
website   | string | Website link of the business|
address   | string | Address of the business | 
city   | string | City of the business  |
state   | string | State of the business |
zip   | string | Zip code of the business |


## Business Details

This API is used for the business details.

```shell
 curl -X GET \
 http://base_url/api/business/:id \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
   }'
```

> The above command returns JSON structured like this:

```json

{
	"business": {
		"id": "1",
		"name": "Pizza Plaza",
		"description": "Good shop",
		"category": "1",
		"subcategory": "1",
		"tag_line": "xyz",
		"offers": "10% discount",
		"image": "plaza.png",
		"phone": "9999999999",
		"website": "plaza.com",
		"address": "street 2,Big mall",
		"city": "Sacamento",
		"state": "Califonia ",
		"zip": "94203"
	}
}

```


###HTTP Request

`GET http://base_url/api/business/:id`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
          |      |           |
 
 
## Business Lists

This API is used for the business Lists.

```shell
 curl -X GET \
 http://base_url/api/subcategory/:id/business\
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
   }'
```

> The above command returns JSON structured like this:

```json

{
	"business": [{
			"id": "1",
			"name": "Pizza Plaza",
			"description": "Good shop",
			"category": "1",
			"subcategory": "1",
			"tag_line": "xyz",
			"offers": "10% discount",
			"image": "plaza.png",
			"phone": "9999999999",
			"website": "plaza.com",
			"address": "street 2,Big mall",
			"city": "Sacamento",
			"state": "Califonia ",
			"zip": "94203"
		},
		{
			"id": "2",
			"name": "Sony Plaza",
			"description": "Great shop",
			"category": "1",
			"subcategory": "1",
			"tag_line": "xyz",
			"offers": "5% discount",
			"image": "song.png",
			"phone": "9999889999",
			"website": "sony.com",
			"address": "street 4,Big mall",
			"city": "Sacamento",
			"state": "Califonia ",
			"zip": "94203"
		}
	]
}
```


###HTTP Request

`GET http://base_url/api/subcategory/:id/business`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
          |      |           | 
 
          