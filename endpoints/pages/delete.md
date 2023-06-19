# Delete Page

Use the DELETE method on `/api/v1/pages` endpoint for delete page by path on a specific site. Only sites created via the API or Custom pages created in the Website editor may be deleted in this way. 

## URL Parameters

You must send a request with the path as a query parameter

```
  /api/v1/pages?page=/delete-me.htm
```

## HTTP Headers

| Name | Required | Description |
| --- | --- | --- |
| x-api-key | Yes | API Key required to authenticate and allow request to perform the operation |
| ddc-site-id | Yes | Site ID that the request is aimed to perform changes |

## Responses

| Code | Error | Message | Addt'l Info |
| --- | --- | --- | --- |
| 200 | Success | DELETE request processed for [siteId] and [page_alias] | |
| 400 | Bad Request | Payload invalid: Path required for DELETE action | |
| 400 | Bad Request | Payload invalid: DELETE only allowed on SITEBUILDER or API pages, please check path | |
| 500 | Internal Server Error | TBD | |

## Sample Call

```
 curl --location --request DELETE 'https://www.domain.com/api/v1/pages?path=/page-to-delete.htm' \
--header 'Accept: application/json' \
--header 'x-api-key: yourProvidedAPIKey' \
--header 'ddc-site-id: targetSiteId' \
--header 'Content-Type: application/json' \
```

* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
