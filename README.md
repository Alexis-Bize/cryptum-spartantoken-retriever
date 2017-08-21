# Cryptum: SpartanToken Retriever
[![N|Solid](https://i.imgur.com/6GvyfVQ.png)](https://www.twitter.com/_SuckMyLuck)

### What is this?
**SpartanToken Retriever** allows anyone to easily retrieve a **v3 SpartanToken Authorization** (X-343-Authorization-Spartan) and start interacting with Halo games API.

### Basic usages
```javascript
import SpartanTokenRetriever from 'cryptum-spartantoken-retriever'

// Requires Xbox LIVE credentials
const SpartanToken = new SpartanTokenRetriever(
    'email@xboxlive.com',
    'password'
);

SpartanToken.retrieve()
.then(spartanToken => console.log(spartanToken))
.catch(error => console.log(error.getFormatedError()));
 
```
Success output:
```javascript
{
   "AccountStatus": 0,
   "SpartanToken": "v3=U:XXXXXX;YYY...",
   "Gamertag": "Le ZeNy",
   "AnalyticsToken": "...",
   "V3Preamble": "v3=",
   "V3Token": "YYY...",
   "Players": [
      {
         "AnalyticsToken": "...",
         "Subject": "U:XXXXXX",
         "Gamertag": "Le ZeNy",
         "Xuid": "...",
         "SpartanClaims": []
      }
   ],
   "ExpiresUtc": {
      "ISO8601Date": "2017-08-21T12:12:00.187Z"
   },
   "Links": [
      {
         "Absolute": false,
         "Relationship": 0,
         "Uri": "/spartan-token"
      }
   ]
}
```
Error output (wrong credentials):
```javascript
{
    code: 11,
    status: 401,
    message: 'Unauthorized',
    reason: 'UNAUTHORIZED'
}
```

### Errors
**Methods:**

* `error.getFormatedError()`
    — Pretty print the last error.
    
* `error.getReason()`:
    — Return error reason.
    
* `error.getCode()`:
    — Return error code.

* `error.getMessage()`:
    — Return error message.

* `error.getStack()`:
    — Return error stack trace.
    
* `error.getHTTPStatus()`:
    — Return error HTTP status.
    
**HTTP Status:**

* 400: Bad Request
* 401: Unauthorized
* 403: Authentication Required
* 500: Internal Error

### Want to contribute?
Feel free to open a pull request or an issue on [GitHub](https://github.com/Alexis-Bize/cryptum-spartantoken)!

### Any questions?
Tweet me at [@_SuckMyLuck](https://www.twitter.com/_SuckMyLuck) or message me on [Reddit](https://www.reddit.com/user/Zeny-/)!

### Licence
MIT