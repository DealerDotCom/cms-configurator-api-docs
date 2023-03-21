# Create Page

Use the `/api/v1/pages` endpoint for creating a new page on a specific site.

## Request Payload

You must `POST` the content used to create the page. An example of a request payload is:

```
  {
    "pageId":  "v9_CONTENT_RAW_FULL_WIDTH_DEFAULT_V1_1", 
    "title": {
      "en_US": "Api Page Title" 
    },
    "path": {
      "en_US": "/api-page-path.html" 
    },
    "addToXMLSitemap": true,
    "addToHTMLSitemap": false,
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

The `pageId` property should be supplied in the payload to the API. You can chose from the pages below and send content associated with each windowId in the `content` block. If content is omitted pages will render as blank pages.

In the example payload above you can see we provided pageId `v9_CONTENT_RAW_FULL_WIDTH_DEFAULT_V1_1` and content windowId `raw-content1`. 
 
| Page ID | Description | Content Window Ids |
| --- | --- | --- |
| v9_CONTENT_RAW_FULL_WIDTH_DEFAULT_V1_1 | Full width page with a page title element and a single raw content area | raw-content1 |
| v9_CONTENT_RAW_FULL_WIDTH_NO_TITLE_V1_1 | Full width page with a single raw content area | raw-content1 |
  
## HTTP Headers

| Name | Required | Description |
| --- | --- | --- |
| x-api-key | Yes | API Key required to authenticate and allow request to perform the operation |
| ddc-site-id | Yes | Site ID that the request is aimed to perform changes |
| x-disable-locale-validation | No | Pass as true for the API to ignore missing locale errors |

## Responses

| Code | Use | Content | Addt'l Info |
| --- | --- | --- | --- |
| 201 | Success | `{ url: "{domain}/your-created-page.html" }` | |
| 206 | Partial Content Success | `{ url: "{domain}/your-created-page.html", message: "Page created but there was an issue saving the following: <issueEncountered>" }` | Do not worry your page has been created. You can try to update your pages content using the [PATCH](./update.md) end point and providing the URL returned from this end point. |
| 406 | Not Acceptable | TBD | |
| 500 | Internal Server Error | TBD | |

## Sample Call

```
 curl --location --request POST 'https://www.domain.com/api/v1/pages' \
--header 'Accept: application/json' \
--header 'x-api-key: yourProvidedAPIKey' \
--header 'ddc-site-id: targetSiteId' \
--header 'Content-Type: application/json' \
--data-raw '{
        "pageId":  "SOURCE_PAGE_ID", 
        "title": {
          "en_US": "Api Page Title"
        },
        "path": {
          "en_US": "/api-page-path.html"
        },
        "addToXMLSitemap": true,
        "addToHTMLSitemap": false,
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
