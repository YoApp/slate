---
title: Flash Polls API

language_tabs:
  - python
  - shell


toc_footers:
  - 
<a href='http://www.flashpolls.com/dashboard/'>Flash Polls Dashboard</a>

search: true
---

# Introduction

Welcome to the Flash Polls API

As a `Publisher` with access to our API, here are the types of objects you can interact with:

* `App`
* `User`
* `Endpoint`
* `Poll`

1.`Publishers` like yourself can have multiple `Apps` under their account.  
2. An `App` is an iOS app that you've integrated the `Flash Polls SDK` into.  
2. A `User` that is using your `App` needs to have an `Endpoint` created for them in order to receive `Polls`.  
3. When you publish a `Poll`, the `Poll` is broadcasted to all the `Endpoints` that are under the `App` of which you published the `Poll` to.  


# Apps

An app object represents an iOS app.
A publisher can have multiple apps.


## Apps - List

```python
import requests


requests.get("http://api.flashpolls.com/publishers/:publisher_id/apps/")

```

```shell
curl "http://api.flashpolls.com/publishers/:publisher_id/apps/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:


```json
{
  "results": [
    {
      "app_token": "1234542234234", 
      "arn_apns": "arn:aws:sns:us-west-2:131325091098:app/APNS_SANDBOX/FlashPollsSDKTest", 
      "created_at": 1466725398, 
      "id": "576c2dc68dd45c75ecc7934e", 
      "name": "Acme News", 
      "publisher": {
        "$oid": "576d74193785b7576f8345a6"
      }, 
      "slug": "acme"
    }, 
    {
      "app_token": "3cc4ab03-86c4-4b13-853b-bea0ceba566b", 
      "arn_apns": "arn:aws:sns:us-west-2:131325091098:app/APNS_SANDBOX/com.flashpolls.acme-times-journal.yo-polls", 
      "created_at": 1467322287, 
      "id": "5775495fe0f5ac099184b318", 
      "name": "Yo Polls", 
      "publisher": {
        "$oid": "576d74193785b7576f8345a6"
      }, 
      "slug": "yo-polls"
    }, 
    {
      "app_token": "049eff5c-75b8-480b-9825-b682d082925b", 
      "created_at": 1468006050, 
      "id": "577fb852cb84ed0003e42bf3", 
      "name": "Yo", 
      "publisher": {
        "$oid": "576d74193785b7576f8345a6"
      }, 
      "slug": "yo"
    }
  ]
}

```




### HTTP Request

`GET http://api.flashpolls.com/publishers/:publisher_id/apps/`





## Apps - Retrieve

```python
import requests


requests.get("http://api.flashpolls.com/apps/:app_id")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:


```json
{
  "description": "Unsupported authorization type", 
  "error": "Invalid JWT header", 
  "status_code": 401
}

```

```json
{
  "app_token": "1234542234234", 
  "arn_apns": "arn:aws:sns:us-west-2:131325091098:app/APNS_SANDBOX/FlashPollsSDKTest", 
  "created_at": 1466725398, 
  "id": "576c2dc68dd45c75ecc7934e", 
  "name": "Acme News", 
  "publisher": {
    "$oid": "576d74193785b7576f8345a6"
  }, 
  "slug": "acme"
}

```




### HTTP Request

`GET http://api.flashpolls.com/apps/:app_id`





## Apps - Create

```python
import requests


requests.post("http://api.flashpolls.com/publishers/:publisher_id/apps/")

```

```shell
curl "http://api.flashpolls.com/publishers/:publisher_id/apps/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:


```json
{
  "app_token": "e1e27806-422b-4b35-9d6b-cd7bb6e4d303", 
  "created_at": 1468104378, 
  "id": "5781386ae0f5ac6a1809a1b8", 
  "name": "Acme News", 
  "publisher": {
    "$oid": "576d74193785b7576f8345a6"
  }, 
  "slug": "acme-news"
}

```

```json
{
  "app_token": "4e22a636-dae0-420e-a421-9978c9d15c9f", 
  "created_at": 1468104401, 
  "id": "57813881e0f5ac6a1f152d58", 
  "name": "Acme News", 
  "publisher": {
    "$oid": "576d74193785b7576f8345a6"
  }, 
  "slug": "acme-news"
}

```




### HTTP Request

`POST http://api.flashpolls.com/publishers/:publisher_id/apps/`




### Attributes

Parameter | Type
--------- | ---- 
name | Acme News




## Apps - Edit

```python
import requests


requests.put("http://api.flashpolls.com/apps/:app_id")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:


```json
{
  "app_token": "4e22a636-dae0-420e-a421-9978c9d15c9f", 
  "created_at": 1468104401, 
  "id": "57813881e0f5ac6a1f152d58", 
  "name": "Acme Headlines", 
  "publisher": {
    "$oid": "576d74193785b7576f8345a6"
  }, 
  "slug": "acme-news"
}

```




### HTTP Request

`PUT http://api.flashpolls.com/apps/:app_id`





## Apps - Delete

```python
import requests


requests.delete("http://api.flashpolls.com/apps/:app_id")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`DELETE http://api.flashpolls.com/apps/:app_id`







# Endpoints




## Endpoint - List

```python
import requests


requests.get("http://api.flashpolls.com/users/:user_id/endpoints/")

```

```shell
curl "http://api.flashpolls.com/users/:user_id/endpoints/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/users/:user_id/endpoints/`





## Endpoint - Retrieve

```python
import requests


requests.get("http://api.flashpolls.com/endpoints/:endpoint_id")

```

```shell
curl "http://api.flashpolls.com/endpoints/:endpoint_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/endpoints/:endpoint_id`





## Endpoint - Create

```python
import requests


requests.post("http://api.flashpolls.com/users/:user_id/endpoints/")

```

```shell
curl "http://api.flashpolls.com/users/:user_id/endpoints/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`POST http://api.flashpolls.com/users/:user_id/endpoints/`




### Attributes

Parameter | Type
--------- | ---- 
push_token | sadf3qr22rw3rq2edwq23refwr23qdfq

platform | ios




## Endpoint - Edit

```python
import requests


requests.put("http://api.flashpolls.com/endpoints/:endpoint_id")

```

```shell
curl "http://api.flashpolls.com/endpoints/:endpoint_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`PUT http://api.flashpolls.com/endpoints/:endpoint_id`





## Endpoint - Delete

```python
import requests


requests.delete("http://api.flashpolls.com/endpoints/:endpoint_id")

```

```shell
curl "http://api.flashpolls.com/endpoints/:endpoint_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`DELETE http://api.flashpolls.com/endpoints/:endpoint_id`







# Polls




## Polls - List

```python
import requests


requests.get("http://api.flashpolls.com/apps/:app_id/polls/")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id/polls/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/apps/:app_id/polls/`





## Polls - Retrieve

```python
import requests


requests.get("http://api.flashpolls.com/polls/:poll_id")

```

```shell
curl "http://api.flashpolls.com/polls/:poll_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/polls/:poll_id`





## Polls - Create

```python
import requests


requests.post("http://api.flashpolls.com/apps/:app_id/polls/")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id/polls/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`POST http://api.flashpolls.com/apps/:app_id/polls/`





## Polls - Edit

```python
import requests


requests.put("http://api.flashpolls.com/polls/:poll_id")

```

```shell
curl "http://api.flashpolls.com/polls/:poll_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`PUT http://api.flashpolls.com/polls/:poll_id`





## Polls - Delete

```python
import requests


requests.delete("http://api.flashpolls.com/polls/:poll_id")

```

```shell
curl "http://api.flashpolls.com/polls/:poll_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`DELETE http://api.flashpolls.com/polls/:poll_id`







# Subscriptions




## Subscriptions - List

```python
import requests


requests.get("http://api.flashpolls.com/topics/:topic_id/subscriptions/")

```

```shell
curl "http://api.flashpolls.com/topics/:topic_id/subscriptions/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/topics/:topic_id/subscriptions/`





## Subscriptions - Retrieve

```python
import requests


requests.get("http://api.flashpolls.com/topics/:topic_id/subscriptions/")

```

```shell
curl "http://api.flashpolls.com/topics/:topic_id/subscriptions/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/topics/:topic_id/subscriptions/`





## Subscriptions - Create

```python
import requests


requests.post("http://api.flashpolls.com/subscriptions/")

```

```shell
curl "http://api.flashpolls.com/subscriptions/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`POST http://api.flashpolls.com/subscriptions/`





## Subscriptions - Edit

```python
import requests


requests.put("http://api.flashpolls.com/subscriptions/:subscription_id")

```

```shell
curl "http://api.flashpolls.com/subscriptions/:subscription_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`PUT http://api.flashpolls.com/subscriptions/:subscription_id`





## Subscriptions - Delete

```python
import requests


requests.delete("http://api.flashpolls.com/subscriptions/:subscription_id")

```

```shell
curl "http://api.flashpolls.com/subscriptions/:subscription_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`DELETE http://api.flashpolls.com/subscriptions/:subscription_id`







# Topics




## Topics - List

```python
import requests


requests.get("http://api.flashpolls.com/apps/:app_id/topics/")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id/topics/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/apps/:app_id/topics/`





## Topics - Retrieve

```python
import requests


requests.get("http://api.flashpolls.com/topics/:topic_id")

```

```shell
curl "http://api.flashpolls.com/topics/:topic_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`GET http://api.flashpolls.com/topics/:topic_id`





## Topics - Create

```python
import requests


requests.post("http://api.flashpolls.com/apps/:app_id/polls/")

```

```shell
curl "http://api.flashpolls.com/apps/:app_id/polls/"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`POST http://api.flashpolls.com/apps/:app_id/polls/`





## Topics - Edit

```python
import requests


requests.put("http://api.flashpolls.com/topics/:topic_id")

```

```shell
curl "http://api.flashpolls.com/topics/:topic_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`PUT http://api.flashpolls.com/topics/:topic_id`





## Topics - Delete

```python
import requests


requests.delete("http://api.flashpolls.com/topics/:topic_id")

```

```shell
curl "http://api.flashpolls.com/topics/:topic_id"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:





### HTTP Request

`DELETE http://api.flashpolls.com/topics/:topic_id`