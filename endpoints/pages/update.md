# Update Page Content/Metadata

  This endpoint works for updating content and metadata on an already existing page.

* **URL**

  /api/{version}/pages?path={path}

* **Method:**
  
  `PATCH`
  
*  **Headers**

   **Required:**
 
   `x-api-key=[string]` - API Key required to authenticate and allow request to perform the operation </br>
   `ddc-site-id=[string]` - Site ID that the request is aimed to perform changes

*  **URL Params**

   **Required:**
 
   `version=[string]` - API version, a string that specifies the version of the API the developer wants to contact. Current valid value is `v1`

   **Optional:**
   
   `path=[string]` - Path to perform updates on. If this does not exist Update will fallback to payload.path

* **Data Params**

```
  {
    "path": {
      "en_US": "/api-page-path.html" 
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
* **Success Response:**

  * **Code:** 201 <br />
    **Content:** `{ url: "{domain}/your-updated-page.html" }`
 
* **Error Response:**

  * **Code:** 406 NOT ACCEPTABLE <br />
    **Content:** TBD

  OR

  * **Code:** 500 INTERNAL SERVER ERROR <br />
    **Content:** TBD
    
> *You may see messages about failures to post metadata and/or content. Your page was still created and you can use the Composer interface to fill out any missing content.*

* **Sample Call:**
```
 curl --location --request POST 'https://www.domain.com/api/v1/pages?path=/existing-page-path.htm' \
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
