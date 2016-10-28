## 1.5. [Content Types](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#content-types) {#1-5-content-types}

**Definition**

1.  A Boundary is defined as the value of the body header named &quot;boundary&quot;

### 1.5.1. [Application/JSON](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#applicationjson) {#1-5-1-application-json}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00127 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which does not have a &quot;Content-Type&quot; header with value &quot;application/json&quot; or &quot;multipart/mixed&quot; |
| XAPI-00128 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which has excess multi-part sections that are not attachments. |
| XAPI-00129 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which is missing multi-part sections for non-fileURL attachments must be rejected. |

### 

###  {#-0}

### 1.5.2. [Multipart/Mixed](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#multipartmixed) {#1-5-2-multipart-mixed}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00130 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and does not have a Boundary before each &quot;Content-Type&quot; header |
| XAPI-00131 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and does not have a body header named &quot;boundary&quot; |
| XAPI-00132 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and for any part except the first does not have a Header named &quot;X-Experience-API-Hash&quot; with a value of one of those found in a &quot;sha2&quot; property of a Statement in the first part of this document |
| XAPI-00133 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and does not have all of the Statements in the first document part |
| XAPI-00134 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and does not the first document part with a &quot;Content-Type&quot; header with a value of &quot;application/json&quot; |
| XAPI-00135 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and for any part except the first does not have a Header named &quot;Content-Transfer-Encoding&quot; with a value of &quot;binary&quot; |
| XAPI-00137 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and does not have a body header named &quot;MIME-Version&quot; with a value of &quot;1.0&quot; or greater |
| XAPI-00138 | An LRS rejects with error code 400 Bad Request, a PUT or POST Request which uses Attachments, has a &quot;Content Type&quot; header with value &quot;multipart/mixed&quot;, and does not have a body header named &quot;Content-Type&quot; with value &quot;multipart/mixed&quot; |