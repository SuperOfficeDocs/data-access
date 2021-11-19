---
title: Endpoints
uid: ws_endpoints
description: Endpoints
author: Bergfrid Dias
so.date: 11.18.2021
keywords: API, web services, endpoints, WebAPI, SOAP
so.topic: concept
---

# Endpoints

## SOAP

## WebAPI

[!include[Intro to the WebAPI](../../../includes/webapi-intro.md)]

### Getting started

* Get the version number and build date from the **API endpoint**: `/api`
* Get a list of supported URLs using the version URL: `/api/v1`

### Authorization

* [Authorization types and how to configure them][3]
* [How to reuse sessions with XSRF-TOKEN][4]

### HTTP request headers

* [Accept-Language][5]
* [Content-Type][6]
* [If-Modified-Since and If-Unmodified-Since][7]

<!-- Referenced links -->
[1]: rest-webapi/index.md
[2]: agents-webapi/index.md
[3]: ../../../authentication/onsite/webapi/index.md#options
[4]: ../../../authentication/onsite/webapi/reuse-session.md
[5]: http-headers.md#accept-language
[6]: http-headers.md#content-type
[7]: http-headers.md#modified-unmodified
