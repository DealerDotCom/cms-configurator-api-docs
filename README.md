**CMS-Configurator API**
----
API for interacting with sites and content hosted on Dealer.com's Content Management System. 

## End Points
End points should include the API version number as part of the path. New versions will be published in the [ReleaseNotes/Changelog](changelog.md)
**TODO: Create/link to changelog** 

| Action | Http Method | URL |
| ---- | ---- | ---- |
| [Create Page](./endpoints/pages/create.md) | POST | /api/{version}/pages |
| [Delete Page](./endpoints/pages/delete.md) | POST | /api/{version}/pages/delete |
  
### Authentication
Calls requires an API Key that can be provided to you by request. The API key request should contain a list of siteIds to be associated with your key. Once given your API you should include this key in your request headers to authenticate. 
**TODO: create/link to getting started guide**

### Rate Limiting 
All calls through the API are subject to rate limiting. Your calls to the API should be prepared to handle retry / load shedding responses. 
**TODO: create/link to page with retry examples**  

### Reporting Issues: 
Issues with this API can be reported by opening a [GitHub Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue). 

### **Notes:**
This API is currently under development and subject to change.
