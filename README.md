# FloppySend Is Way More Than Just Connecting.

Floppysend is committed to being the ultimate email blast and bulk SMS services provider worldwide with high-quality and exceptional support. Floppysend marketing tools and features empower your business’s marketing efforts, drive more leads, and convert them to long-term customers. 



## FloppySend's APIs

Use our simple APIs to integrate SMS text messaging, Email and more services with your already existing business applications and systems. 

[FloppySend](https://floppysend.com/apiReferences) offers a range of APIs to allow programmers to design software to interact and integrate with our service. In some cases, existing software with the necessary capability can simply be configured to use one of our APIs, without any custom coding needed. 


### FloppySend SMS API

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
  - To: String, Required, number/numbers sending to.
  - From: String, Required, sender which will appear to the user.
  - Dcs: String, Required, if message contains unicode: 8, if message doenst contain unicode: 0.
  - Text: String, Required, message body.
  - Sched: String, Optional, iso format.

#### SMS API Responses
```
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

```
//PHP Code Sample

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
