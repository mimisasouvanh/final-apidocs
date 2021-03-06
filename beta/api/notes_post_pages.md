# Create page

Create a new OneNote page in the default section of the default notebook.

The `POST /notes/pages` operation is supported only when creating pages in the current user's default notebook. If you're targeting group notebooks, you can [create pages in a specific section](../api/section_post_pages.md).           
### Prerequisites
One of the following **scopes** is required to execute this API:  
Notes.Create, Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All
### HTTP request
<!-- { "blockType": "ignored" } -->

```http
POST /me/notes/pages
POST /users/<mail>/notes/pages
POST /users/<objectId>/notes/pages
POST /groups/<objectId>/notes/pages
```

### Request headers  
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | `Bearer <token>` A valid OAuth token provided to the app based on the user credentials and the user having authorized access. |
| Content-Type | string | `text/html` or `application/xhtml+xml` for the HTML content, including for the required "Presentation" part of multipart requests. Multipart requests use the `multipart/form-data; boundary=your-boundary` content type. |

### Request body
In the request body, supply the HTML content for the page.

The body can contain HTML placed directly in the request body, or it can contain a multipart message format as shown in the example. If you're sending binary data, then you must send a multipart request.

### Response
If successful, this method returns a `201 Created` response code and the new [page](../resources/page.md) object in the response body.

### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "create_page_from_notes"
}-->
```http
POST https://graph.microsoft.com/v1.0/me/notes/pages
Content-type: application/json
Content-length: 312

{
  "title": "title-value",
  "createdByAppId": "createdByAppId-value",
  "links": {
    "oneNoteClientUrl": {
      "href": "href-value"
    },
    "oneNoteWebUrl": {
      "href": "href-value"
    }
  },
  "contentUrl": "contentUrl-value",
  "content": "content-value",
  "lastModifiedTime": "datetime-value"
}
```
In the request body, supply a JSON representation of [page](../resources/page.md) object.
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.page"
} -->
```http
Content-type: application/json
Content-length: 312

{
  "title": "title-value",
  "createdByAppId": "createdByAppId-value",
  "links": {
    "oneNoteClientUrl": {
      "href": "href-value"
    },
    "oneNoteWebUrl": {
      "href": "href-value"
    }
  },
  "contentUrl": "contentUrl-value",
  "content": "content-value",
  "lastModifiedTime": "datetime-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Create Page",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->