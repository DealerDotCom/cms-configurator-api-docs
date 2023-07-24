# Get Page

Use the GET method on `/api/v1/pages` endpoint to retrieve the page configuration for the provided siteId. If no page is found will return a 404

## URL Parameters

You must send a request with the path as a query parameter

```
  /api/v1/pages?page=/index.htm
```

## HTTP Headers

| Name | Required | Description |
| --- | --- | --- |
| x-api-key | Yes | API Key required to authenticate and allow request to perform the operation |
| ddc-site-id | Yes | Site ID that the request is aimed to perform changes |

## Responses

| Code | Error | Message | Addt'l Info |
| --- | --- | --- | --- |
| 200 | Success | { pageJSON } | |
| 400 | Bad Request | Payload invalid: Path required for GET action | |
| 404 | Not Found | No page found for provided path | |
| 500 | Internal Server Error | TBD | |

## Sample Call

```
 curl --location --request GET 'https://www.domain.com/api/v1/pages?path=/index.htm' \
--header 'Accept: application/json' \
--header 'x-api-key: yourProvidedAPIKey' \
--header 'ddc-site-id: targetSiteId' \
--header 'Content-Type: application/json' \
```
## Sample Response
```
{
    "alias": "INDEX",
    "pageId": "INDEX_LANDING_0002_V1_5",
    "path": "/index.htm",
    "pathsByLocale": {
        "es_US": "/index.htm",
        "fr_CA": "/index.htm",
        "en_US": "/index.htm"
    },
    "content": {
         "content1": {
            "siteId": "meeseeksdemo",
            "contentId": "ce7f931af7af4373befecc44b42487ff",
            "languages": [
                "en_US"
            ],
            "content": {
                "en_US":  "Here at [Dealership Name] --  Meeseeks' Code Box Demo, it is our mission to be the automotive home of drivers in the Burlington, VT area. We provide a vast selection of new and used vehicles, exceptional car care and customer service with a smile.<p><font face=\"DDC Heading Font Face\" size=\"3\"><br></font>Speaking of <a href=\"/new-inventory/index.htm\">new [Dealership Make] models</a>, you have your pick of our showroom. Our local dealership keeps a great stock of <a href=\"/used-inventory/index.htm\">used cars, trucks, and SUVs</a> in inventory. With competitive prices offered on every pre-owned model for sale on our lot, you won't find a reason to visit any other dealership in Btv VT. </p>"
            }
        }
    },
    "metadata": {
        "title": {
            "en_US": "[Company Name] | [Company Type] [Landing Make]  in [Company City], [Company State] "
        },
        "description": {
            "en_US": "[Dealership Name] sells and services [Dealership Make] vehicles in the greater [Dealership City] [Dealership State] area. "
        },
        "keywords": {
            "en_US": "Meeseeks' site for demos"
        }
    }
}
```
* **Notes:**

 This endpoint is still under construction and continuous improvement, so please note that the specs and definitions may change.
