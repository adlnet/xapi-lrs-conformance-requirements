## 2.2. [Formatting Requirements](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#dataconstraints) {#2-2-formatting-requirements}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00001 | An LRS rejects with error code 400 Bad Request any Statement having a property whose value is set to &quot;null&quot;, an empty object, or has no value, except in an &quot;extensions&quot; property |
| XAPI-00002 | An LRS stores 32-bit floating point numbers with at least the precision of IEEE 754 |
| XAPI-00003 | An LRS rejects with error code 400 Bad Request a Statement which does not contain an &quot;actor&quot; property |
| XAPI-00004 | An LRS rejects with error code 400 Bad Request a Statement which does not contain a &quot;verb&quot; property |
| XAPI-00005 | An LRS rejects with error code 400 Bad Request a Statement which does not contain an &quot;object&quot; property |
| XAPI-00006 | An LRS rejects with error code 400 Bad Request a Statement which uses the wrong data type |
| XAPI-00007 | An LRS rejects with error code 400 Bad Request a Statement which uses any non-format-following key or value, including the empty string, where a string with a particular format (such as mailto IRI, UUID, or IRI) is required. |
| XAPI-00008 | An LRS rejects with error code 400 Bad Request a Statement where the case of a key does not match the case specified in this specification. |
| XAPI-00009 | An LRS rejects with error code 400 Bad Request a Statement where the case of a value restricted to enumerated values does not match an enumerated value given in this specification exactly. |
| XAPI-00010 | An LRS rejects with error code 400 Bad Request a Statement where a key or value is not allowed by this specification. |
| XAPI-00011 | An LRS rejects with error code 400 Bad Request a Statement containing IRL or IRI values without a scheme. |
| XAPI-00012 | The LRS rejects with error code 400 Bad Request parameter values which do not validate to the same standards required for values of the same types in Statements. |
| XAPI-00013 | The LRS rejects with error code 400 Bad Request a token with does not validate as matching the RFC 5646 standard in the sequence of token lengths for language map keys. |
| XAPI-00014 | All Objects are well-created JSON Objects (Nature of Binding) |
| XAPI-00015 | All Strings are encoded and interpreted as UTF-8 |