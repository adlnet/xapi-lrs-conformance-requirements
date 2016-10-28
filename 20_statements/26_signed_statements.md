## 2.6. [Signed Statements](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#signature) {#2-6-signed-statements}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00115 | A Signed Statement MUST include a JSON web signature (JWS) as defined here:[http://tools.ietf.org/html/rfc7515](http://tools.ietf.org/html/rfc7515), as an Attachment with a usageType of http://adlnet.gov/expapi/attachments/signature and a contentType of application/octet-stream. The LRS must reject with 400 a statement which has usageType of http://adlnet.gov/expapi/attachments/signature and a contentType of application/octet-stream but does not have a signature attached. |
| XAPI-00116 | The JWS signature MUST have a payload of a valid JSON serialization of the complete Statement before the signature was added.The LRS must reject with 400 a statement which does not have a valid JSON serialization. |
| XAPI-00117 | The JWS signature MUST use an algorithm of &quot;RS256&quot;, &quot;RS384&quot;, or &quot;RS512&quot;. The LRS must reject with 400 a statement which does not use one of these algorithms or does not use one of these algorithms correctly. |