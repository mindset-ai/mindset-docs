# Mindset API

Mindset provides two API protocols which achieve the same objective. The protocol choice is up to you based on your personal or project preferences.

* [gRPC API](gprc-api.md)
* [REST API](rest-api/)

If you are familiar with [gRPC](https://grpc.io/), then this is the preferred approach. If you are more comfortable with [REST](https://en.wikipedia.org/wiki/REST), Mindset fully supports this.&#x20;

Note: All underlying Mindset APIs are gPRC based. There is a transcription process at our API gateway which provisions REST APIs from our gRPC containers. The REST endpoints front the gRPC endpoints. Conversion between REST and gRPC is handled automatically.&#x20;
