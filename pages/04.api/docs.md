---
title: 'API Reference'
---

This API follows the [JSON: API](http://jsonapi.org) specification.

#### Errors
This API returns standard HTTP errors. A `2XX` response code indicates that the API was successful in whatever action was requested. A `4XX` error indicates authentication or data validation issues. The API will return a `504` error if it is unable to talk to the daemon for certain actions, and a general `500` error for anything else.