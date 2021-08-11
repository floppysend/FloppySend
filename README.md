# FloppySend Is Way More Than Just Connecting.

Floppysend is committed to being the ultimate email blast and bulk SMS services provider worldwide with high-quality and exceptional support. Floppysend marketing tools and features empower your business’s marketing efforts, drive more leads, and convert them to long-term customers. 



## FloppySend's APIs

Use our simple APIs to integrate SMS text messaging, Email and more services with your already existing business applications and systems. 

[FloppySend](https://floppysend.com/apiReferences) offers a range of APIs to allow programmers to design software to interact and integrate with our service. In some cases, existing software with the necessary capability can simply be configured to use one of our APIs, without any custom coding needed. 


### FloppySend SMS API ( New Version )

FloppySend's SMS API is well-defined software interface which enables code to send short messages via a SMS Gateway. Use our simple SMS APIs to integrate SMS text messaging with your already existing business applications and systems. 

Request Types
 - GET: If the request is get method you need to append params as query string inside the params section
 - POST: If request is post method you need to append params as x-www-form-urlencoded inside the body of the request

```
https://api.floppy.ai/sms
```
```
{
    X-api-key:"Your x-api-key" (string required)
    X-Secret-Hash:"Your x-secret-hash" 
    (string required if added from dashboard)
}
```
You can get your X-Api-Key And X-Secret-Hash from your [account setting](https://app.floppysend.com/) page in Api Keys section

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | To | String | Yes | number/numbers sending to |
  | From | String | Yes | sender which will appear to the user |
  | Dcs | String | Yes | if message contains unicode: 8, if message doenst contain unicode: 0 |
  | Text | String | Yes | message body |
  | Sched | String | Optional | iso format |

#### SMS API Responses
```JSON
{
    "Result": "Success",
    "Datainfo": 
    [
        {
            "Status": "Sent",
            "ID": "Response_Id",
            "Error_Code": "0",
            "Error_Desc": "0"
        }
    ]
}
```

#### SMS API Code Sample

```PHP
//PHP

<?php

$curl = curl_init();
curl_setopt_array($curl, array(
    CURLOPT_URL => 'https://api.floppy.ai/sms',
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_ENCODING => '',
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 0,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
    CURLOPT_CUSTOMREQUEST => 'POST',
    CURLOPT_POSTFIELDS =>
    'to={to_number}&from={sender}&dcs={dcs}&text={message_body}&sched=2021-07-02T11%3A16%3A28',
    CURLOPT_HTTPHEADER => array(
    'x-api-key: "Your x-api-key"',
    'Content-Type: application/x-www-form-urlencoded'
                                ),
    ));
$response = curl_exec($curl);
curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"
url = URI("https://api.floppy.ai/sms")
https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true
request = Net::HTTP::Post.new(url)
request["x-api-key"] = "Your x-api-key"
request["Content-Type"] = "application/x-www-form-urlencoded"
request.body =
"to={to_number}&from={sender}&dcs={dcs}&text={message_body}&sched=2021-07-02T11%3A16%3A28"
response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
.build();
MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType,
"to={to_number}&from={sender}&dcs={dcs}&text={message_body}&sched=2021-07-02T11:16:28");
Request request = new Request.Builder()
.url("https://api.floppy.ai/sms")
.method("POST", body)
.addHeader("x-api-key", "Your x-api-key")
.addHeader("Content-Type", "application/x-www-form-urlencoded")
.build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://api.floppy.ai/sms");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("x-api-key", "Your x-api-key");
request.AddHeader("Content-Type", "application/x-www-form-urlencoded");
request.AddParameter("to", "{to_number}");
request.AddParameter("from", "{sender}");
request.AddParameter("dcs", "{dcs}");
request.AddParameter("text", "{message_body}");
request.AddParameter("sched", "2021-07-02T11:16:28");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
    'to': 'TO-NUMBER',
    'from': 'FROM-SENDER',
    'dcs': '0',
    'text': 'MESSAGE-BODY',
    'sched': 'Time-IsoFormat'
});
var config = {
    method: 'post',
    url: 'https://api.floppy.ai/sms',
    headers: {
        'x-api-key': 'YOUR-API-KEY',
        'Content-Type': 'application/x-www-form-urlencoded'
    },
    data: data
};

axios(config)
    .then(function (response) {
        console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
        console.log(error);
    });
```



### FloppySend SMS API ( Old Version )
FloppySend provide APIs for SMS in old version, where user can use username & password as request parameters, 
you may get your SMS legacy password from your [accoutn dashboard](https://app.floppysend.com/) at Legacy Api settings. 

Request Types
 - GET: If the request is get method you need to append params as query string inside the params section
 - POST: If request is post method you need to append params as x-www-form-urlencoded inside the body of the request

```
https://api.floppy.ai/smslegacy
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | Username | String | Yes | username for the user can be seen in the account page under legacy tab |
  | Password | String | Yes | password for the user can be seen in the account page under legacy tab which the user can change |
  | To | String | Yes | | number/numbers sending to |
  | From | String | Yes | sender which will appear to the user |
  | Dcs | String | Yes | if message contains unicode: 8, if message doenst contain unicode: 0 |
  | Text | String | Yes | message body |
  | Sched | String | Optional | iso format |
  
#### SMS Legancy API Responses
```JSON
{
    "Result": "Success",
    "Datainfo": 
    [
        {
            "Status": "Sent",
            "ID": "Response_Id",
            "Error_Code": "0",
            "Error_Desc": "0"
        }
    ]
}                   
```

#### SMS Legancy API Code Sample
```PHP
//PHP

<?php

$curl = curl_init();
curl_setopt_array($curl, array(
        CURLOPT_URL => 'https://api.floppy.ai/smslegacy',
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_ENCODING => '',
        CURLOPT_MAXREDIRS => 10,
        CURLOPT_TIMEOUT => 0,
        CURLOPT_FOLLOWLOCATION => true,
        CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
        CURLOPT_CUSTOMREQUEST => 'POST',
        CURLOPT_POSTFIELDS =>
        'username={your_user_name}&password={your_password}&to={to_number}&from={sender}&dcs={dcs}&text={message_body}',
        CURLOPT_HTTPHEADER => array(
        'Content-Type: application/x-www-form-urlencoded'
        ),
    ));
$response = curl_exec($curl);
curl_close($curl);
echo $response;
```

```Ruby
//Ruby

require "uri"
require "net/http"
url = URI("https://api.floppy.ai/smslegacy")
https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true
request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/x-www-form-urlencoded"
request.body =
"username={your_username}&password={your_password}&to={to_number}&from={sender}&dcs={dcs}&text={message_body}"
response = https.request(request)
puts response.read_body
```

```Java
//JAVA
//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
.build();
MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType,
"username={your_username}&password={your_password}&to={to_number}&from={sender}&dcs={dcs}&text={message_body}");
Request request = new Request.Builder()
.url("https://api.floppy.ai/smslegacy")
.method("POST", body)
.addHeader("Content-Type", "application/x-www-form-urlencoded")
.build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://api.floppy.ai/smslegacy");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/x-www-form-urlencoded");
request.AddParameter("username", "{your_username}");
request.AddParameter("password", "{your_password}");
request.AddParameter("to", "{to_number}");
request.AddParameter("from", "{sender}");
request.AddParameter("dcs", "{dcs}");
request.AddParameter("text", "{message_body}");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```Javascript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
'username': 'YOUR-USER-NAME',
'password': 'YOUR-PASSWORD',
'to': 'TO-NUMBER',
'from': 'FROM-SENDER',
'dcs': '0',
'text': 'MESSAGE-BODY',
'sched': 'Time-IsoFormat' 
});

var config = {
  method: 'post',
  url: 'https://api.floppy.ai/smslegacy',
  headers: { 
    'Content-Type': 'application/x-www-form-urlencoded'
  },
  data : data
};

axios(config)
     .then(function (response) {
       console.log(JSON.stringify(response.data));
     })
     .catch(function (error) {
       console.log(error);
     });
```

### FloppySend Integrating with SMPP


Short Message Peer-to-Peer (SMPP) is an industry-standard protocol for exchanging short messages and data between systems.

SMPP defines operation and protocol data units (PDUs), where every operation has a request PDU and an associated response PDU. The only exception is for alert notifications, which do not require an associated response PDU. The receiving entity must send the associated response to the SMPP PDU request.

FloppySend supports version 3.4 of the SMPP protocol, [Read more...](https://floppysend.com/apiReferences#SMPP)


### API Rate Limiting
To protect the platform from being overloaded and maintain a high quality of service to all customers, 
FloppySend API applies rate limits for its SMS API, [Read more...](https://floppysend.com/apiReferences)

### Email to SMS
Documentation of how to send emails to SMS.
To use this service, you need to whitelist your company email address or an entire domain, 
at your [account dashboard](https://app.floppysend.com) for sending SMSes, [Read more...](https://floppysend.com/apiReferences)

### FloppySend Webhook

Webhooks are "user-defined HTTP callbacks". They are usually triggered by some event, such as receiving, failure or rejected messages.

When that event occurs, FloppySend makes an HTTP Post request to the URL configured for the webhook. Users can configure them 
at [account dashboard](https://app.floppysend.com) >> Webhooks section, [Read more...](https://floppysend.com/apiReferences)


### FloppySend Balance API
Get your current balance for FloppySend Services with simple API

Request Types
 - GET METHOD
 - POST METHOD

```
https://api.floppy.ai/balance
```
```
{
    X-api-key:"Your x-api-key" (string required)
    X-Secret-Hash:"Your x-secret-hash" 
    (string required if added from dashboard)
}
```
You can get your X-Api-Key And X-Secret-Hash, from your [account setting](https://app.floppysend.com) page in Api Keys section 

#### Balance Response
```
{
    "Result": "Success",
    "Datainfo": [
        {
            "Balance": "{your_balance}",
            "Currency": "{balance_currency}"
        }
    ]
}
```


#### Balance API Code Sample
```PHP
//PHP

<?php

$curl = curl_init();
curl_setopt_array($curl, array(
        CURLOPT_URL => 'https://api.floppy.ai/balance',
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_ENCODING => '',
        CURLOPT_MAXREDIRS => 10,
        CURLOPT_TIMEOUT => 0,
        CURLOPT_FOLLOWLOCATION => true,
        CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
        CURLOPT_CUSTOMREQUEST => 'POST',
        CURLOPT_HTTPHEADER => array(
        'x-api-key: "Your x-api-key"',
        'Content-Length: 0'
        ),
    ));
$response = curl_exec($curl);
curl_close($curl);
echo $response;
```

```Ruby
//Ruby

require "uri"
require "net/http"
url = URI("https://api.floppy.ai/balance")
https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true
request = Net::HTTP::Post.new(url)
request["x-api-key"] = "Your x-api-key"
response = https.request(request)
puts response.read_body
```

```Java
//Java
//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
.build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
.url("https://api.floppy.ai/balance")
.method("POST", body)
.addHeader("x-api-key", "Your x-api-key")
.build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://api.floppy.ai/balance");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("x-api-key", "Your x-api-key");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);te(request);
Console.WriteLine(response.Content);
```

```Javascript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request
                            
var axios = require('axios');

var config = {
  method: 'post',
  url: 'https://api.floppy.ai/balance',
  headers: { 
    'x-api-key': 'YOUR-API-KEY'
  }
};

axios(config)
     .then(function (response) {
       console.log(JSON.stringify(response.data));
     })
     .catch(function (error) {
       console.log(error);
     });
```                        

