## 4.1. [Extensions](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#miscext) {#4-1-extensions}

**Definitions**

1.  An Extension is defined as an Object of any &quot;extensions&quot; property

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00118 | An Extension &quot;key&quot; is an IRI. The LRS rejects with 400 a statement which has an extension key which is not a valid IRI, if an extension object is present. |
| XAPI-00119 | An Extension can be null, an empty string, objects with nothing in them. The LRS accepts with 200 if a PUT or 204 if a POST an otherwise valid statement which has any extension value including null, an empty string, or an empty object. |
| XAPI-00120 | An Extension&#039;s structure is that of &quot;key&quot;/&quot;value&quot; pairs. The LRS rejects with 400 a statement which does not use valid “key”/”value” pairs in the Extension property |