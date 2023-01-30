**Delete Page**
----
Method call to remove a sitemap entry from a given site

* **URL**
/api/{version}/pages/delete

* **Method:**
  `POST`
  
*  **Headers**

   **Required:**
 
   `x-api-key=[string]` - API Key required to authenticate and allow request to perform the operation </br>
   `ddc-site-id=[string]` - Site ID that the request is aimed to perform changes
  
* **Data Params** Requires JSON payload with following properties 
  
  **Required:**
 
   `path=[string]`

* **Success Response:**

  * **Code:** 501 NOT_IMPLEMENTED <br />
    **Content:** `{ id : 12 }`
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "Not Authorized, please provide API key" }`

  OR

  * **Code:** 422 UNPROCESSABLE ENTRY <br />
    **Content:** `{ error : "Email Invalid" }`

* **Sample Call:**

  **TODO: Fill out when delete implemented for real**
* **Notes:**
Method is not yet implemented will return 501 for authorized callers 
