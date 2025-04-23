# Context Files API

## POST <a href="#post" id="post"></a>

Create a new file in a context

#### externalId \[string] <a href="#externalid-string" id="externalid-string"></a>

When synchronising content from an external source this field can be used to track an id in the source system.

If you provide a value for this field then the API will enforce uniqueness of items with this ID. To update content for an externalId you must first delete any existing item.

#### name \[string] <a href="#name-string" id="name-string"></a>

This is the name that will be used for this file when it is shown to the end user in some way. This could be through content discovery, as a source or citation in an agent response. It is also the name shown in the admin UI

#### mimeType \[string] (one of the listed below value) <a href="#mimetype-string-one-of-the-listed-below-value" id="mimetype-string-one-of-the-listed-below-value"></a>

This should be the mime type of the content you are sending for ingestion.

* Some content types have to be sent in the request body - using `documentContent`
* Some content types have to be stored externally with a URL sent to the API, so that it can in turn download them for ingestion - using `sourceUrl`
* Most content types will have a format conversion performed on the content during ingestion.
* Some content types can be viewed using inbuilt functionality

&#x20;

**text/plain**

* Content must be in `documentContent`
  * cannot be viewed using built in viewer?

**text/html**

* Content can be in `documentContent`
  * Content provided this way will be converted to markdown text for better agent understanding
  * Only text in the provided content will be ingested
  * cannot be viewed using built in viewer
* Content can be provided as a link to an external web page in `sourceUrl`
  * Content provided this way will be converted to PDF by printing the external page
  * Can be viewed using internal viewer, but not recommended for web pages converted to PDF

**video/mp4**

* Content must be downloadable from a URL provided in `sourceUrl`
  * can be viewed using built in viewer
  * Only audio is transcribed during ingestion. Videos without speech (or an unrecognised codec) will result in ingestion failure
  * No conversion, upscaling or downscaling takes place, so if you wish end users to view this content then make sure it suitable for playing on the devices & bandwidth requirements you expect for your users

**audio/mpeg**

* Content must be downloadable from a URL provided in `sourceUrl`
  * can be played using built in viewer

**application/pdf**

* Content (for small PDFs) can be provided base64 encoded in `documentContent`
  * can be viewed using built in viewer
* Content can be downloadable from the URL provided in `sourceUrl`
  * can be viewed using built in viewer

**application/vnd.openxmlformats-officedocument.presentationml.presentation**

* Content must be downloadable from a URL provided in `sourceUrl`
  * Content will be converted to PDF during ingestion
  * can be viewed using built in viewer

**application/vnd.openxmlformats-officedocument.wordprocessingml.document**

* Content must be downloadable from a URL provided in `sourceUrl`
  * Content will be converted to PDF during ingestion
  * can be viewed using built in viewer

#### &#x20;sourceUrl \[string]  <a href="#sourceurl-string" id="sourceurl-string"></a>

A URL from which files for ingestion can be downloaded, or for web pages opened for printing to PDF.

If the file exists in a Google Drive then this URL should be the URL to the file itself in Drive, and the file should be shared with download permission to Mindset’s Google service account.

Otherwise the URL should be freely accessible without authentication.

Do not provide both this and `documentContent`

#### documentContent \[string] <a href="#documentcontent-string" id="documentcontent-string"></a>

Some mime types allow sending the content of to be ingested in the same request.

Do not provide both this and `sourceUrl`

&#x20;

#### autoPublish \[Boolean] <a href="#autopublish-boolean" id="autopublish-boolean"></a>

After successful ingestion of content the knowledge in the content can be shared to agents & end users. This is called “publishing”

For a fully automatic process that makes content available to end users as soon as possible set this to true.

If a final review is needed to check details in the admin UI then provide false here. It will require manual intervention from an admin to make each file ultimately available.

#### hideContentSegments \[Boolean] <a href="#hidecontentsegments-boolean" id="hidecontentsegments-boolean"></a>

For published files allow the agent to use the knowledge in the files, but never to directly provide this file to an end user.

This can be updated later

#### knownAs \[String] <a href="#knownas-string" id="knownas-string"></a>

How the agent can refer to this content item. eg 'video', 'discussion', 'sales pitch'

#### externalUrl \[String] <a href="#externalurl-string" id="externalurl-string"></a>

An external URL to direct an end user to the content for this document.

If `viewOriginalSource` is true then when a user is present with this content through discovery as a citation or source then this URL will be opened in a browser tab.

This URL can contain variables which will be replaced with specific values for the current user.

This URL does not need to be unrestricted. If your agent is embedded in a site requiring a log in and this URL is also on that site the logged in (to your site) user will have a seamless experience.

The ingestion process does not use this URL to extract any content.

#### thumbnailUrl \[String] <a href="#thumbnailurl-string" id="thumbnailurl-string"></a>

A URL for an optional thumbnail to apply to a content item.\
If no thumbnail is provided then a default thumbnail will be used.

If provided it should point to a small (up to 3MB) freely accessible image.\
The image will be copied and served from our storage when used in our UI

Do not provide both this and `thumbnail`

If fetching the file fails, or the image is too big, then the entire request to ingest this file will fail.

#### thumbnail \[String] <a href="#thumbnail-string" id="thumbnail-string"></a>

It is also possible to provide a base64 encoded png for use as the file thumbnail.

A base64 encoded image to use as a thumbnail for this content.

Do not provide both this and `thumbnailUrl`

#### viewOriginalSource \[Boolean] <a href="#vieworiginalsource-boolean" id="vieworiginalsource-boolean"></a>

This tells the agent UI to launch the provided `externalUrl` in a new tab when a user access a content card, segment or citation from this content item.

If the `externalUrl` is missing or invalid then the end user will see an error when they try to access a citation / source etc from this file

#### contentHash \[String] <a href="#contenthash-string" id="contenthash-string"></a>

Sometimes content changes and the calling process needs to be able to decide if it needs to update the content ingested through this API.

This is a string that is recorded for a file only during creation, but available afterwards.\
It is something that should be sent by the caller.

It could be a timestamp string of the when the file is modified. If that does not match the data in the source location then the calling process can decide to replace the item.

It could be a checksum calculated from the binary content of the source file.

It is left to the calling process to choose a value from the source information store that is meaningful and easy to access.

&#x20;

#### labels \[Array of String] <a href="#labels-array-of-string" id="labels-array-of-string"></a>

It is possible to apply up to 10 labels to a content item.

labels themselves are managed through the Labels API, and through the admin UI

When applied to a file a single list of up to 10 uids is stored in the content item.

No validation is performed whether the labels exist and/or the uids are valid. Invalid (or no longer valid) uids are ignored at run time.

This list can be written or overwritten only as an entire list of labels. If you wish to add or remove a particular label then you could write code to first query the list and then save a modified version.

#### &#x20;runId \[String] <a href="#runid-string" id="runid-string"></a>

Content items are rarely sent individually - more usually as part of an automated process running against a collection of source documents.

This field allows you to store a string for all content items sent during a particular process.

It is not used internally by Mindset’s code, but you can use it in queries for current status of items - eg to query the current status of all items sent in a previous ingestion cycle to check for any errors.

&#x20;

## PATCH <a href="#patch" id="patch"></a>

&#x20;

This endpoint is used to update some data for a file that has already been created.

You can generally update most of the metadata around an item that is used to control how it is displayed to the end user.

You cannot update the content of the item. If the content has changed then the old file should be deleted and a new one ingested.

If you do not send a value for one of the fields then no change will be made to that field.

If you do send a value then all fields should be valid or the request will fail and nothing will be updated.

The fields you can send are listed below.

The format & validation rules are the same as for POSTing a new file

#### name \[String] <a href="#name-string" id="name-string"></a>

#### hideContentSegments \[Boolean] <a href="#hidecontentsegments-boolean-.1" id="hidecontentsegments-boolean-.1"></a>

#### knownAs \[String] <a href="#knownas-string-.1" id="knownas-string-.1"></a>

#### externalUrl \[String] <a href="#externalurl-string-.1" id="externalurl-string-.1"></a>

#### viewOriginalSource \[Boolean] <a href="#vieworiginalsource-boolean-.1" id="vieworiginalsource-boolean-.1"></a>

#### labels \[Array of string] <a href="#labels-array-of-string" id="labels-array-of-string"></a>

#### thumbnailUrl \[String] <a href="#thumbnailurl-string-.1" id="thumbnailurl-string-.1"></a>

#### thumbnail \[String] <a href="#thumbnail-string-.1" id="thumbnail-string-.1"></a>

&#x20;

## GET <a href="#get" id="get"></a>

### Querying for multiple items <a href="#querying-for-multiple-items" id="querying-for-multiple-items"></a>

You can call the main GET endpoint to query for multiple files in a context.

The response is paginated - you will get a limited number of items in each request. You can then make subsequent requests to the next batch of files.

Files are sorted in order of `createdAt`

#### startAfter - Querying for “the next page” \[String] <a href="#startafter-querying-for-the-next-page-string" id="startafter-querying-for-the-next-page-string"></a>

Use the `startAfter` parameter and provide the `createdAt` string of the last file in the current results set

When there are no more results you will receive an empty array in the response and a 404 status code

#### runId \[String] <a href="#runid-string-.1" id="runid-string-.1"></a>

You can query just for files created during an execution cycle using the string id you passed in as the `runId` parameter to POST

#### status \[String] <a href="#status-string" id="status-string"></a>

Apart from the initial “accepted” status you can query for any other possible status of files ingested.

A useful query would be to query for status of “fail” which a file will get if ingestion of its content could not complete.

This filtering can be combined with a runId filter

### Response data <a href="#response-data" id="response-data"></a>

You will get the same data describing a file when querying for a list of them, or querying for a specific one using a uid or externalId

This data is also returned from a successful POST to create a new file, or PATCH to update an existing one.

#### uid \[String] <a href="#uid-string" id="uid-string"></a>

The uid of the file. This cannot be changed.

#### externalId \[String] <a href="#externalid-string" id="externalid-string"></a>

The externalId provided for the file at creation time. This ID cannot be changed, and the API will reject a request to ingest another file with the same externalId.

To ingest updated content first delete the file using this externalId, and then you will be able to create another.

If no externalId was specified then this will be an empty string.

#### createdAt \[Iso timestamp] <a href="#createdat-iso-timestamp" id="createdat-iso-timestamp"></a>

The ISO 8601 timestamp of when this file was first accepted through the API, used mainly for paginating requests to retrieve multiple files.

#### name \[String] <a href="#name-string-.1" id="name-string-.1"></a>

The name displayed to end users.

#### status \[String] <a href="#status-string-.1" id="status-string-.1"></a>

The ingestion status of the file.

“accepted” is the status you get before the file itself has been fully copied into the system.

This is the only status you cannot specifically query for when requesting all files with a given status

You can query for “fail” “readyForPublication” and “published”

#### runId \[String] <a href="#runid-string-.2" id="runid-string-.2"></a>

To aid matching files in Mindset with files created during a particular execution of your code calling the API you can pass an ID string here that will be stored for each file.

You can query the Files API and filter to files matching a specified runId

#### mimeType \[String] <a href="#mimetype-string" id="mimetype-string"></a>

This is the mimeType of the file as it was when its content was processed for ingestion.

For some input file types this will have been changed from what was originally sent to the API.

For example `text/html` files that are to be gathered from web pages, the file actually processed will be a PDF generated by printing that web page

#### autoPublish \[Boolean] <a href="#autopublish-boolean-.1" id="autopublish-boolean-.1"></a>

Once this is set during file creation it cannot be changed.

#### hideContentSegments \[Boolean] <a href="#hidecontentsegments-boolean-.2" id="hidecontentsegments-boolean-.2"></a>

This can be updated

#### contentHash \[String] <a href="#contenthash-string-.1" id="contenthash-string-.1"></a>

This cannot be changed and is the string provided at the point of initial content ingestion.

This is key to your code being able to decide if the content previously ingested from one of your source documents is out of date.

#### knownAs \[String] <a href="#knownas-string-.2" id="knownas-string-.2"></a>

You can provide a custom description of how this file is described. Eg if it is a video recording it might be “webinar” or “conference speech”\
\


#### externalUrl \[String] <a href="#externalurl-string-.2" id="externalurl-string-.2"></a>

If `viewOriginalSource` is true, the agent suggests this file as relevant to its reply and the user clicks on that segment / citation / source in the UI then the UI will open this URL.

&#x20;

#### viewOriginalSource \[Boolean] <a href="#vieworiginalsource-boolean-.2" id="vieworiginalsource-boolean-.2"></a>

Tells the agent to not use the in app player, but to open the externalUrl in a browser tab.

Do not set this to true unless you have provided a valid URL in `externalUrl`

#### thumbnailUpdatedByAdmin \[Boolean] <a href="#thumbnailupdatedbyadmin-boolean" id="thumbnailupdatedbyadmin-boolean"></a>

&#x20;

&#x20;

## DELETE <a href="#delete" id="delete"></a>

You can delete a file within a context by providing the file uid.

&#x20;

&#x20;

## FAQs <a href="#faqs" id="faqs"></a>

### How to ingest a file ignoring any thumbnail error <a href="#how-to-ingest-a-file-ignoring-any-thumbnail-error" id="how-to-ingest-a-file-ignoring-any-thumbnail-error"></a>

The API is very strict. If it detects an invalid thumbnail is sent to the POST endpoint then it will abort the entire request.

If it is important that the content is only made available with the thumbnail then you should send all information in the POST request.

If you do not care if the thumbnail fails to ingest then make two sequential calls:

* POST to create start the file ingestion. Do not specify any thumbnail here
* PATCH to update the file you just created applying a thumbnail. You are free to ignore failures here and the content will still be processed

### An admin updated the thumbnail. I do not want to overwrite the admin user’s choice <a href="#an-admin-updated-the-thumbnail.-i-do-not-want-to-overwrite-the-admin-users-choice" id="an-admin-updated-the-thumbnail.-i-do-not-want-to-overwrite-the-admin-users-choice"></a>

Check thumbnailUpdatedByAdmin for the document in a GET response before sending a new thumbnail in a PATCH request

If the thumbnail had been changed by a human then your code can choose to skip the update.

If you overwrite the thumbnail through the API then this boolean will also get reset.

&#x20;

### The content in a file has changed. How do I update the content of a file in Mindset? <a href="#the-content-in-a-file-has-changed.-how-do-i-update-the-content-of-a-file-in-mindset" id="the-content-in-a-file-has-changed.-how-do-i-update-the-content-of-a-file-in-mindset"></a>

You can’t directly ingest fresh content over an existing file in Mindset.

You can find the corresponding Mindset file to your source file using an externalId.

Compare the `contentHash` string you sent originally with the appropriate value for you file now.

If they are different then you can delete the current file and create a new one for the same externalId

If you wish you can copy over values for knownAs, name, etc to the newly created file.

It is not yet possible to copy over the thumbnail.
