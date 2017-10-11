# Authentication

## Signup

This API is used for the signup with mobile numbers.

```shell
 curl -X POST \
 http://baseurl/api/signup \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "users": {
           "mobile_number":"9999999999"
             }
}'
```

> The above command returns JSON structured like this:

```json
{
  "otp" :"2345" 
}
```
> JSON Error like this:

```json
{
  "error": [
    "Please enter the correct mobile number."
  ]
}

```

###HTTP Request

`POST http://base_url/api/signup`

### URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
mobile_number |string |	Mobile number of the user|	true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>



## OTP Verification

This API is used for the OTP verification.

```shell
 curl -X POST \
 http://baseurl/api/otp \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "users": {
           "otp":"2345"
             }
}'
```

> The above command returns JSON structured like this:

```json
{
	"users": {
	    "id"  :"1",
		"mobile": "9999999999",
		"email" :"",
		"name": "",
		"city": "",
		"state": "",
		"zip": "",
		"pic" :""
	},
	 "access_token": "AABBCCDD",
     "refresh_token": "DDCCBBAA"
}
```
> JSON Error like this:

```json
{
  "error": [
    "Please enter the correct OTP number."
  ]
}
```

###HTTP Request

`POST http://base_url/api/otp`

### URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
 otp      |string|	OTP number for mobile verification |	true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Login with facebook

This API is used for login with facebook.

```shell
  curl -X POST \
 http://baseurl/api/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "users": {
          "social" :"facebook",
          "token": "facebooktoken",
             }
}'
```

> The above command returns JSON structured like this:

```json
{
	"users": {
	    "id"  :"1",
		"mobile": "",
		"email" :"user@gmail.com",
		"name": "",
		"city": "",
		"state": "",
		"zip": "",
		"pic" :""
	},
	 "access_token": "AABBCCDD",
     "refresh_token": "DDCCBBAA"
}

```


###HTTP Request

`POST http://base_url/api/signin`

### URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
facebook  | boolen | Face book value  | true
token | string | Token value of the user | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Login with Twitter

This API is used for login with Twitter.


```shell
  curl -X POST \
 http://baseurl/api/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "users": {
          "social" :"twitter",
          "token": "twittertoken",
             }
}'
```

> The above command returns JSON structured like this:

```json
{
	"users": {
	    "id"  :"1",
		"mobile": "",
		"email" :"user@gmail.com",
		"name": "",
		"city": "",
		"state": "",
		"zip": "",
		"pic" :""
	},
	 "access_token": "AABBCCDD",
     "refresh_token": "DDCCBBAA"
}

```


###HTTP Request

`POST http://base_url/api/signin`

### URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
twitter  | boolen | Twitter value  | true
token | string | Token value of the user | true




## Create Location 

This API is used for enter the location details.

```shell
 curl -X POST \
 http://baseurl/api/location \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
    "users": {
        "zip" :	"94203",
        "state": "California",
        "city" : "Sacamento",	
             }
}'

```

> The above command returns JSON structured like this:

```json
{
	"users": {
	    "id"  :"1",
		"mobile": "",
		"email" :"user@gmail.com",
		"name": "",
		"city": "Sacamento",
		"state": "California",
		"zip": "94203"
	},
	 "access_token": "AABBCCDD",
     "refresh_token": "DDCCBBAA"
}
```


###HTTP Request

`POST http://base_url/api/location`

### URL Parameters

Parameter | Type | Description | Required
--------- |------|-----------|---------
zip  | string | Zip code of the user | true
state | string | State of the user | true
city | string | City of the user | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>