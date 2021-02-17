---
title: Stark Developer Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - php
  - ruby
  - python
  - javascript
  - csharp
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

# Libraries

## Xamarin SDK

```csharp
CreateTransaction createtxt = new CreateTransaction();
createtxt.amount = amount.Text.ToString();
createtxt.currency = selectedcurrency;
createtxt.description = description.Text.ToString();
createtxt.redirectUrl = redirectUrl.Text.ToString();
createtxt.reference = reference.Text.ToString();
dynamic txtData = Transaction.CreateTransaction("key_test_bc60487f0cb789d79e281359d21e9eb7321a16ce",createtxt);
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
}
else
{
String str = "";
foreach (string field in txtData.metadata.fields)
{
str += field + "\n";
}
await DisplayAlert("Message", str + txtData.metadata.message, "OK");
}
}
else
{
await DisplayAlert("Message", "Something went wrong!", "OK");
```

Before you start using the Xamarin SDK for Android or iOS, You need to have an Account with Stark and a store along with an API key created VIA our Dashboard.

### Quickstart

```csharp
<StackLayout Margin="30" VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
<StackLayout HorizontalOptions="FillAndExpand" VerticalOptions="CenterAndExpand">
<Label FontSize="30" HorizontalOptions="CenterAndExpand">Transaction Detail</Label>
<StackLayout Orientation="Horizontal">
<Label FontSize="20">TransactionId :</Label>
<Label x:Name="transactionId" FontSize="20">null</Label>
</StackLayout>
<StackLayout Orientation="Horizontal">
<Label FontSize="20">Amount :</Label>
<Label x:Name="amount" FontSize="20">null</Label>
</StackLayout>
<StackLayout Orientation="Horizontal">
<Label FontSize="20">status :</Label>
<Label x:Name="status" FontSize="20">null</Label>
</StackLayout>
<StackLayout Orientation="Horizontal">
<Label FontSize="20">Mode:</Label>
<Label x:Name="mode" FontSize="20">null</Label>
</StackLayout>

<forms:ZXingBarcodeImageView
x:Name="generatedqrcode"
BarcodeFormat="QR_CODE"
BarcodeValue="1234"
HeightRequest="300"
WidthRequest="300">
<zx:ZXingBarcodeImageView.BarcodeOptions>
<zxcm:EncodingOptions Width="300" Height="300"/>
</zx:ZXingBarcodeImageView.BarcodeOptions>
</forms:ZXingBarcodeImageView>
<Button x:Name="paytransaction" Text="Pay" BackgroundColor="RoyalBlue" BorderWidth="1" TextColor="White" BorderColor="DarkBlue" Clicked="paytransaction_Clicked" CornerRadius="15"/>
</StackLayout>
</StackLayout>
</pages:PopupPage>
```


Steps | Description
--------- | ------- | -----------
1 |Prepare the Project | 
2 |Set up the Sample |
3 |Run the Sample |

### Preqreuisites
<ul>
  <li>Visual Studio 2013 or later</li>
  <li>Starkpayments account with a store and an API key</li>
</ul>

###  Prepare the Project

To use this SDK, you need to have the following prerequisites: 
<ul>
  <li>Create a new C# Xamarin Application in Visual Studio</li>
  <li>Open the Nuget Package Manager Console, Select the package source nuget.org, and run the following command:</li>
</ul>
<aside class="success">
Install-Package Coinstream-payments
</aside>

### Set up the Sample
After successful installation of the nuget package, call in the Starkpayments' SDK's methods to Create or GET a transaction like the example to the right.


Stark's Payment SDK for Xamarin uses ZXING library as a dependency to generate the QrCodes on the runtime and display them on the app. To achieve that , Simply pass the amount to the method using the View element as:

### Run the Sample
Once the Package is integrated with your Application, build and run the sample by clicking start in the Visual studio toolbar. You should now be able to Create transactions with QrCodes and Get the desired transactions.





