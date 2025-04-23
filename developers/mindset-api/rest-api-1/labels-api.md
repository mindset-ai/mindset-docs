# Labels API

## POST <a href="#post" id="post"></a>

Create a new label (which can be assigned later to a Context File)

#### name (String) <a href="#name-string" id="name-string"></a>

Displayed name of the label

#### externalId (string) <a href="#externalid-string" id="externalid-string"></a>

Unique Identifier of the label you can optionally provide

#### **showInDiscovery** (Boolean) <a href="#showindiscovery-boolean" id="showindiscovery-boolean"></a>

Is this label will be visible to the end users ?

&#x20;

## PATCH <a href="#patch" id="patch"></a>

This method and endpoints using it are used for updating a Label updatable values.

#### name (String) <a href="#name-string-.1" id="name-string-.1"></a>

Displayed name of the label

#### **showInDiscovery** (Boolean) <a href="#showindiscovery-boolean-.1" id="showindiscovery-boolean-.1"></a>

Is this label will be visible to the end users ?

&#x20;

## GET <a href="#get" id="get"></a>

You can call the main GET endpoint to query the list of labels or get label individually

#### startAfter - Querying for “the next page” \[String] <a href="#startafter-querying-for-the-next-page-string" id="startafter-querying-for-the-next-page-string"></a>

Use the `startAfter` parameter and provide the `createdAt` string of the last label in the current results set

When there are no more results you will receive an empty array in the response and a 404 status code

&#x20;

## DELETE <a href="#delete" id="delete"></a>

You can delete a label by providing its uid

&#x20;

## RESPONSE DATA <a href="#response-data" id="response-data"></a>

You will get the same response data when calling POST, PATCH or GET

#### uid (string) <a href="#uid-string" id="uid-string"></a>

Mindset internal label uid

#### externalId (string) <a href="#externalid-string-.1" id="externalid-string-.1"></a>

Unique Identifier of the label you can optionally provide

#### name (String) <a href="#name-string-.2" id="name-string-.2"></a>

Displayed name of the label

#### **showInDiscovery** (Boolean) <a href="#showindiscovery-boolean-.2" id="showindiscovery-boolean-.2"></a>

Will this label be visible to the end users ?

#### createdAt (ISO timestamp) <a href="#createdat-iso-timestamp" id="createdat-iso-timestamp"></a>

Label creation date
