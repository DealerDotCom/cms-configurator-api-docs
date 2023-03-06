**Delete Page**
----
Method call to remove a sitemap entry from a given site

* **URL**
/api/{version}/pages

* **Method:**
  `DELETE`
  
*  **Headers**

   **Required:**
 
   `x-api-key=[string]` - API Key required to authenticate and allow request to perform the operation </br>
   `ddc-site-id=[string]` - Site ID that the request is aimed to perform changes
  
* **URL Params**
  
  **Required:**
 
   `path=[string]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `DELETE request processed for [siteId] and [page_alias]`
 
* **Error Response:**

  * **Code:** 400 BAD REQUEST <br />
    **Content:** `Payload invalid: Path required for DELETE action`

  OR

  * **Code:** 500 INTERNAL SERVER ERROR <br />
    **Content:** Server Error Message

* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
