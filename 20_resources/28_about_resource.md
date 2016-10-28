## 2.8. [About Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#aboutresource) {#2-8-about-resource}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00315 | An LRS has an About API with endpoint &quot;base IRI&quot;+&quot;/about&quot; |
| XAPI-00316 | An LRS&#039;s About API&#039;s version property can only have values of &quot;0.9&quot;, &quot;0.95&quot;, &quot;1.0.0&quot;, or “1.0.x” with |
| XAPI-00317 | An LRS&#039;s About API&#039;s version property contains at least one string of &quot;1.0.x&quot; |
| XAPI-00318 | An LRS&#039;s About API&#039;s version property is an array of strings |
| XAPI-00319 | An LRS&#039;s About Resource accepts GET requests. Upon processing a successful GET request returns a version property and code 200 OK |
| XAPI-00320 | An LRS&#039;s About API upon processing a successful GET request can return an Extension Object with code 200 OK |
| XAPI-00321 | An LRS rejects with error code 400 Bad Request, a Request which does not use a &quot;X-Experience-API-Version&quot; header name to any API except the About API |