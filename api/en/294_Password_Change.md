# Change Password(\_\_mypassword)

## Overview

An API that performs operations on the account's password

### Change password of own account

Change password of your account.  
\* The Account update API can also change the password of the Account, but this requires the auth authority of the cell level ACL and uses it for management purposes.  
\* Because of changes to the account, CellLocalToken by account authentication is mandatory, not UnitUserToken.

### Required Privileges

None


## Request

### Request URL

```
{CellName}/__mypassword
```

### Request Method

PUT

### Request Query

None

### Request Header

|Header Name|Overview|Effective Value|Required|Notes|
|:--|:--|:--|:--|:--|
|Authorization|Specifies authentication information in the OAuth 2.0 format|Bearer {CellLocalToken}|Yes|The authentication token is a cell local token acquired by the authentication token acquisition API|
|X-Personium-Credential|Password after change|String|Yes|Number of character:6 - 92<br>Character type: Single-byte alphanumeric characters, hyphens ("-"), and underscores ("_")|

### Request Body

None


## Response

### Response Code

204

### Response Header

None

### Response Body

None

### Error Messages

Refer to [Error Message List](004_Error_Messages.md)


## cURL Command

```sh
curl "https://cell1.unit1.example/__mypassword" -X PUT -i -H \
'X-Personium-Credential: change_password' -H 'Authorization: Bearer AA~4l...(snip)........auMhw' -H \
'Accept: application/json'
```


