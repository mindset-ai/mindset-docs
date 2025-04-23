# Contexts API

## POST <a href="#post" id="post"></a>

Create a new context

#### name \[String] <a href="#name-string" id="name-string"></a>

Displayed name of the context

#### description \[String] <a href="#description-string" id="description-string"></a>

Description of the context

#### externalId \[String] <a href="#externalid-string" id="externalid-string"></a>

Unique Identifier of the context you can optionally provide

#### isSynced \[Boolean] <a href="#issynced-boolean" id="issynced-boolean"></a>

When a context is synced, files ingestion are synced with automatic mechanism (external process).\
Hence, the files ingested in the context cannot be managed manually via the Mindset App admin portal.

&#x20;

## PATCH <a href="#patch" id="patch"></a>

This method and endpoints using it are used for updating a context values.

#### name \[String] <a href="#name-string-.1" id="name-string-.1"></a>

Displayed name of the context

#### description \[String] <a href="#description-string-.1" id="description-string-.1"></a>

Description of the context

&#x20;

## GET <a href="#get" id="get"></a>

You can call the main GET endpoint to query the list of contexts or get context individually

#### startAfter - Querying for “the next page” \[String] <a href="#startafter-querying-for-the-next-page-string" id="startafter-querying-for-the-next-page-string"></a>

Use the `startAfter` parameter and provide the `createdAt` string of the last context in the current results set

When there are no more results you will receive an empty array in the response and a 404 status code

&#x20;

## DELETE <a href="#delete" id="delete"></a>

You can delete a context by providing its uid\
Note: You cannot delete a context containing files. You will receive a 422 response code if you try.

&#x20;

## RESPONSE DATA <a href="#response-data" id="response-data"></a>

You will get the same response data when calling POST, PATCH or GET

#### uid \[string] <a href="#uid-string" id="uid-string"></a>

Mindset internal context uid

#### externalId \[string] <a href="#externalid-string" id="externalid-string"></a>

Unique Identifier of the context you can optionally provide

#### name \[String] <a href="#name-string-.2" id="name-string-.2"></a>

Displayed name of the context

#### description \[String] <a href="#description-string-.2" id="description-string-.2"></a>

Description of the context

#### createdAt \[ISO timestamp] <a href="#createdat-iso-timestamp" id="createdat-iso-timestamp"></a>

Context creation date

#### isSynced \[Boolean] <a href="#issynced-boolean-.1" id="issynced-boolean-.1"></a>
