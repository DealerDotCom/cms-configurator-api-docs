# Update Page Content/Metadata

This endpoint works for updating content and metadata on an already existing page.

`/api/{version}/pages?path={path}`
## Query Param 
*Optional:*
**path** - path of page to update, if not provided payload must contain a paths by locale property as seen below
## Request Payload

You must `PATCH` the content and/or metadata to update on the page. An example of a request payload is:
```
  {
    "path": {
      "en_US": "/api-page-path.htm" 
    },
    "metadata": {
      "title": {
        "en_US": "META TITLE"
      },
      "description": {
        "en_US": "META DESCRIPTION"
      },
      "keywords": {
        "en_US":  "METATAGS1 METATAGS2"
      }
    },
    "content": {
      "raw-content1": { // corresponds to named content areas in individual pages ( page config documented in API )
        "en_US": "<div class='dynamic-content **'/>"
      }
    }
  }
```

## HTTP Headers

| Name | Required | Description |
| --- | --- | --- |
| x-api-key | Yes | API Key required to authenticate and allow request to perform the operation |
| ddc-site-id | Yes | Site ID that the request is aimed to perform changes |
| x-disable-locale-validation | No | Pass as true for the API to ignore missing locale errors |

## Responses

| Code | Use | Content | Addt'l Info |
| --- | --- | --- | --- |
| 201 | Success | `{ url: "{domain}/your-created-page.htm" }` | |
| 206 | Partial Content Success | `{ url: "{domain}/your-created-page.htm", message: "There was an issue saving the following: <issueEncountered>" }` | |
| 406 | Not Acceptable | TBD | |
| 500 | Internal Server Error | TBD | |

## Sample Call

```
 curl --location --request PATCH 'https://www.domain.com/api/v1/pages?path=/existing-page-path.htm' \
--header 'Accept: application/json' \
--header 'x-api-key: yourProvidedAPIKey' \
--header 'ddc-site-id: yoursiteid' \
--header 'Content-Type: application/json' \
--data-raw '{
        "metadata": {
          "title": {
            "en_US": "META TITLE"
          },
          "description": {
            "en_US": "META DESCRIPTION"
          },
          "keywords": {
            "en_US":  "METATAGS1 METATAGS2"
          }
        },
        "content": {
          "raw-content1": {
            "en_US": "<div class='\''dynamic-content **'\''/>"
          }
        }
      }'
```


* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
