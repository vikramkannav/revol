# Review

## Create Review

This API is used for Create Review.

```shell
 curl -X POST \
 http://base_url/api/bisness/:id/review \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
     "reviews": {
          "review": "test review"
    }
   }'
```

> The above command returns JSON structured like this:

```json
{
	"reviews": {
		"id": "1",
		"business_id": "1",
		"review": "test review"
	}
}

```


###HTTP Request

`POST http://base_url/api/bisness/:id/review`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|-----------
review    | string |Review for the business|



## Review Lists

This API is used for list of review.

```shell
 curl -X GET \
 http://base_url/api/business/:id/reviews \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
     "reviews": [{
            "id": "1",
            "business_id": "1",
            "review": "first review"
        },
        {
            "id": "2",
            "business_id": "1",
            "review": "second review"
        }
     ]
   }'


```

> The above command returns JSON structured like this:

```json
{
	"reviews": [{
			"id": "1",
			"business_id": "1",
			"review": "first review"
		},
		{
			"id": "2",
			"business_id": "1",
			"review": "second review"
		}
	]
}

```


###HTTP Request

`GET http://base_url/api/business/:id/reviews`

###URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|-----------
          |      |           | 
