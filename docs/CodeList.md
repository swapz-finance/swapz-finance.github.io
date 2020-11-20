# Code List

## Language
|`lang`|Description|
|-|-|
|en|English|
|zh|Simplified Chinese|
|id|Indonesian|

## Contact Country Code
Customer contact number must comes with country code in [Payment Request](DappIntegration.md#payment-request). We suggest using [libphonenumber](https://github.com/google/libphonenumber), a phone number parser by Google to parse customer's contact number and obtain the contact country code. The **ONLY** country code format accepted is [ISO-3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2). You may checkout their [Github](https://github.com/google/libphonenumber).


## Token

|`tokenId`|Token|Divisibility|
|-|-|-|
|btc|Bitcoin|8|
|eth|Ether|8|
|usdt|USD Tether|6|


## Return Code

|Code|Message|
|--- |--- |
|20000|SUCCESSFUL|
|||
|21000|Invalid DAPP API Key|
|21001|Signature not match|
|21002|Invalid Token ID|
|21003|User contact no. must come with country code|
|21004|Invalid contact or country code|
|21005|Invalid email|
|21006|Invalid language|
|21007|Invalid response url|
|21008|Invalid backend url|
|21009|Duplicated order ID|
|21010|Record not found|
|21011|Invalid amount|
|21012|Payment failed|
|21013|Duplicated withdrawal|
|21014|Customer\'s DAPP token does not exist|
|21015|Insufficient balance|
|21016|Minimum amount not meet|
|||
|29999|SERVER ERROR|



