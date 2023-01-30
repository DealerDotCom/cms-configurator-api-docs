**Create Page**

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
```
  {
    "siteId": "targetSiteId",
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
      "raw-content1": { // corresponds to named content areas in individual pages ( page config documented in API )
        "en_US": "<div class='dynamic-content **'/>"
      },
      "raw-content2": {
        "en_US": "<div class='dynamic-content some-other-identifier-class'/>"
      },
      "raw-content3": {
        "en_US": ""
      }
    }
  }
```
* **Success Response:**

  * **Code:** 201 <br />
    **Content:** `{ url: "{domain}/your-created-page.html" }`
 
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
--header 'Content-Type: application/json' \
--data-raw '{
        "siteId": "targetSiteId",
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
          },
          "raw-content2": {
            "en_US": "<div class='\''dynamic-content some-other-identifier-class'\''/>"
          },
          "raw-content3": {
            "en_US": ""
          }
        }
      }'
```
* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
