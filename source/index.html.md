---
title: Stark Developer Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - php
  - ruby
  - python
  - javascript
  - C#

toc_footers:
  - <a href='https://dashboard.starkpayments.net'>Get an API Key</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to Stark's API and developer documentation. Here you will find useful guides, code examples and links to SDKs that will enable you to easily create crypto payment requests, configure webhooks so that you may accept cryptocurrencies such as bitcoin as a payment method on your website/app.

Stark currently supports the processing of Bitcoin, Ethereum, BitcoinCash, Litecoin and Dash. We are currently working on an advanced integration to have XRP available to merchants.

A Bitcoin Testnet is also available for anyone looking to test bitcoin transactions without having to physically transfer bitcoin.

This documentation will be updated on a regular basis. Please check back for updates.

### Getting started

Before you get started with implementing our API, it's important to first create and have your account verified...including the test one :-)

- Create a new account or login at: <a href='https://dashboard.starkpayments.net'> Stark Merchant Dashboard</a>
- Verify your registered email address
- Complete your Profile
- Add a Business + Website URL
- Generate a Test or Live API key

```C#
CreateTransaction("key_test_bc60487f0cb789d79e281359d21e9eb7321a16ce",createtxt);
if (txtData != null)
{
if (txtData.success)
{
Preferences.Set("transactionId", txtData.transactionId);
Preferences.Set("amount", txtData.amount);
Preferences.Set("status", txtData.status);
Preferences.Set("mode", txtData.mode);
Preferences.Set("links", txtData.links);
Preferences.Set("qrcodetext", txtData.qrcodetext);
_ = PopupNavigation.PushAsync(new Popups.PopupViewTransaction());
//Device.OpenUri(new Uri(txtData.links));
}
else
```

# Payment API

This API allows developer's to Create Payments and retrieve Transaction Details.

## Create Payment

Stark currently supports the processing of Bitcoin, Ethereum, BitcoinCash, Litecoin and Dash. We are currently working on an advanced integration to have XRP available to merchants.

## Transaction Details

Stark currently supports the processing of Bitcoin, Ethereum, BitcoinCash, Litecoin and Dash. We are currently working on an advanced integration to have XRP available to merchants.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

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
curl "http://example.com/api/kittens/2" \
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
curl "http://example.com/api/kittens/2" \
  -X DELETE \
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

