## 4.2. [Language Maps](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#lang-maps) {#4-2-language-maps}

**Definition**

1.  A Language Map is defined as an array of language tag/String pairs has at least 1 entry Implicit

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00121 | A Language Map follows RFC 5646\. The LRS rejects with 400 a statement using a Language Map which doesn’t not validate to RFC 5646\. |