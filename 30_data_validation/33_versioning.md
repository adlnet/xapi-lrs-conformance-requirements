## 3.3 [Versioning](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#versioning) {#3-3-versioning}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00330 | An LRS will not modify Statements based on a &quot;version&quot; before &quot;1.0.1&quot; |
| XAPI-00331 | An LRS rejects with error code 400 Bad Request, a Request which the &quot;X-Experience-API-Version&quot; header&#039;s value is anything but &quot;1.0&quot; or &quot;1.0.x&quot;, where x is the semantic versioning number to any API except the About API |
| XAPI-00332 | Statements returned by an LRS MUST retain the version property they are accepted with. |
| XAPI-00333 | An LRS sends a header response with &quot;X-Experience-API-Version&quot; as the name and latest patch version after 1.0.0 as the value |