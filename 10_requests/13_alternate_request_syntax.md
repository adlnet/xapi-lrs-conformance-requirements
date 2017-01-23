## 1.3. [Alternate Request Syntax](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#alt-request-syntax) {#1-3-alternate-request-syntax}

**Definition**

1.  One of the goals of the xAPI is to allow cross-domain tracking, and even though xAPI seeks to enable tracking from applications other than browsers, browsers still need to be supported. For example, Internet Explorer 8 and 9 do not implement Cross Origin Resource Sharing, but rather use their own Cross Domain Request API, which cannot use all of the xAPI as described above due to only supporting "GET" and "POST", and not allowing HTTP headers to be set.

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00336 | The LRS MUST support the Alternate Request Syntax. |
