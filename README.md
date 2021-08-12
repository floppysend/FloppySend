# FloppySend Is Way More Than Just Connecting.

Floppysend is committed to being the ultimate email blast and bulk SMS services provider worldwide with high-quality and exceptional support. Floppysend marketing tools and features empower your business’s marketing efforts, drive more leads, and convert them to long-term customers. 



## FloppySend's APIs

Use our simple APIs to integrate SMS text messaging, Email and more services with your already existing business applications and systems. 

[FloppySend](https://floppysend.com/apiReferences) offers a range of APIs to allow programmers to design software to interact and integrate with our service. In some cases, existing software with the necessary capability can simply be configured to use one of our APIs, without any custom coding needed. 





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
```JSON
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

