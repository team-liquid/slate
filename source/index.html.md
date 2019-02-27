---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - ruby

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This is the official documentation for Liquid Gold's API. This is meant to be private information and should not be shared.

Liquid Gold is the core API responsible for all fan-based interaction event tracking. At its core, Liquid Gold is responsible for point assignment and distribution. It allows any and all registered Team Liquid users to be rewarded for their interactions with Team Liquid whether that is via Twitch.tv, Youtube, Discord, Instragram, Facebook, and other social media platforms.

The API only supports end points pertaining to a specific user specified. You cannot view points of more than one user at a time.

To view the details of the interaction that awarded the points, that needs to be done through the API of the platform service.

# Authentication

To be updated.

# Points

## Get Points for a User

This endpoint retrieves all points for a user.

### HTTP Request

`GET http://liquidgoldapi.com/api/v1/users/:user_id/points`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
start_date | nil | Takes string of format: MM//DD/YYYY. If entered, will only look for points accrued after and including start date
end_date | nil | Takes string of format: MM//DD/YYYY. If entered, will only look for points accrued before and including end date

## Get Points for a User for a specific platform

This endpoint retrieves all points for a user for a specific platform.

### HTTP Request

`GET http://liquidgoldapi.com/api/v1/users/:user_id/:platform/points`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
start_date | nil | Takes string of format: MM//DD/YYYY. If entered, will only look for points accrued after and including start date
end_date | nil | Takes string of format: MM//DD/YYYY. If entered, will only look for points accrued before and including end date

<!-- <aside class="success"> -->
<!-- Remember — a happy kitten is an authenticated kitten! -->
<!-- </aside> -->

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

