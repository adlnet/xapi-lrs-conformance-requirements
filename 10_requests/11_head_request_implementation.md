## 1.1. [HEAD Request Implementation](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#httphead) {#1-1-head-request-implementation}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00125 | An LRS responds to a HEAD request in the same way as a GET request, but without the message-body. This means run ALL GET tests with HEAD |
| XAPI-00126 | An LRS accepts HEAD requests. |