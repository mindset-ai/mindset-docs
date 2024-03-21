# api-getappuid

A simple method that can be used to check the health of your API key

## Path

`/api-getappuid`

## GET

No query parameters needed

### Response

#### 200

JSON body containing a value for appUid

Indicates your key is valid

#### 401

Missing API Key

#### 403

Invalid API Key
