**CMS-Configurator API**
----
API for interacting with sites and content hosted on Dealer.com's Content Management System. 

## End Points
End points should include the API version number as part of the path. New versions will be published in the [Release Notes](./release-notes.md)

| Action | Http Method | URL |
| ---- | ---- | ---- |
| [Create Page](./endpoints/pages/create.md) | POST | /api/{version}/pages |
| [Delete Page](./endpoints/pages/delete.md) | DELETE | /api/{version}/pages |
| [Update Page Contents](./endpoints/pages/update.md) | PATCH | /api/{version}/pages |
  
### Authentication
Calls requires an API Key that can be provided to you by request. The API key request should contain a list of siteIds to be associated with your key. Once given your API you should include this key in your request headers to authenticate. 
#### Authentication Error Response:
* Code: 401 Unauthorized
```
{
    "message": "Unauthorized"
}
```
* Code: 403 Forbidden
Content: 
```{
    "Message": "User is not authorized to access this resource with an explicit deny"
}
```
**TODO: create/link to getting started guide**

### CORS
This api is [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) enabled.

If specific domains need to be allowed for CORS requests, please contact your Dealer.com rep.

### Rate Limiting 
All calls through the API are subject to rate limiting. Your calls to the API should be prepared to handle retry / load shedding responses. 
**TODO: create/link to page with retry examples**  

### Reporting Issues: 
Issues with this API can be reported by opening a [GitHub Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue). 

### **Notes:**
This API is currently under development and subject to change.
