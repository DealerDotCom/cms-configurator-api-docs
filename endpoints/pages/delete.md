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
  
* **Data Params** Requires JSON payload with following properties 
  
  **Required:**
 
   `path=[string]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `DELETE request received for [siteId] and [page_alias]`
 
* **Error Response:**

  * **Code:** 400 BAD REQUEST <br />
    **Content:** Client Error Message

  OR

  * **Code:** 500 INTERNAL SERVER ERROR <br />
    **Content:** Server Error Message

* **Sample Call:**

* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
