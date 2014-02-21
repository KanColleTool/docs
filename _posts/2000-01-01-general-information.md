---
title: General Information

layout: nil
---

This is unofficial documentation for the API KanColle uses to work.

On one hand, the API is simple, all data is readily available as plain, uncomplicated JSON.  
On the other, all assets are in SWF files, and the whole API gives the word "redundant" a whole new meaning.

### Authorization
The whole API requires authorization in the form of the admiral's API Token, eg. the api_token parameter in their "API Link". Admirals' data is not shared between servers, so talking to the wrong one will get you the same error as if you used the wrong token.

### Requests
Requests are form encoded (they use PHP on the server side), with two required, omnipresent parameters:

* **api_token**: The admiral's API Token, used for authorization
* **api_verno**: The API Version (always **1**)

Requests are sent to the admiral's "home server", with the path prefix **/kcsapi/**.

### Responses
Responses are JSON encoded, Unicode characters are escaped, and it's all prefixed with "svdata=". The data is embedded in an "envelope", looking something like:

`{
	"api_result": 1,
	"api_result_msg": "\u6210\u529f",
	"api_data": ...
}`

**api_data** is usually used for the response data, though there are exceptions (gah) where this variable is named something else, and even ones with multiple variables for response data.

### Result Codes
The currently known error codes are:

* 1 - Success
* 200 - Invalid Credentials

(stub)
