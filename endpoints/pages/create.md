# Create Page

  This endpoint works for creating a new page in a specific Site.

* **URL**

  /api/{version}/pages

* **Method:**
  
  `POST`
  
*  **Headers**

   **Required:**
 
   `x-api-key=[string]` - API Key required to authenticate and allow request to perform the operation </br>
   `ddc-site-id=[string]` - Site ID that the request is aimed to perform changes

*  **URL Params**

   **Required:**
 
   `version=[string]` - API version, a string that specifies the version of the API the developer wants to contact. Current valid value is `v1`

   **Optional:**
 
   No optional parameters supported.

* **Data Params**
[See available pages](#available-pages) for available layouts and their windowIds
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
* **Success Response:**

  * **Code:** 201 <br />
    **Content:** `{ url: "{domain}/your-created-page.html" }`
 
* **Partial Content Success Response:**
  * **Code:** 206 <br />
    **Content:** `{ url: "{domain}/your-created-page.html", message: "Page created but there was an issue saving the following: <issueEncountered>" }`
> *In the event of a partial content response do not worry your page has been created. You can try to update your pages content using the [PATCH](./update.md) end point and providing the URL returned from this end point. 
 
* **Error Response:**

  * **Code:** 406 NOT ACCEPTABLE <br />
    **Content:** TBD

  OR

  * **Code:** 500 INTERNAL SERVER ERROR <br />
    **Content:** TBD

* **Sample Call:**
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

### Available Pages
**pageId** property should be supplied in the payload to the API. You can chose from the pages below and send content associated with each windowId in the **content** block. If content is omitted pages will render as blank pages. <br/> In the example payload above you can see we provided pageId: v9_CONTENT_RAW_FULL_WIDTH_DEFAULT_V1_1 and content windowId "raw-content1" 
 
| PageID | Description | Content WindowIds |
| ----- | ----- | ----- |
| v9_CONTENT_RAW_FULL_WIDTH_DEFAULT_V1_1 | Full width page with a page title element and a single raw content area | "raw-content1" |
| v9_CONTENT_RAW_FULL_WIDTH_NO_TITLE_V1_1 | Full width page with a single raw content area | "raw-content1" |


* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
