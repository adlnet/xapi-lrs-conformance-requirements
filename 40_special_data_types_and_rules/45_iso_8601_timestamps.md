## 4.5. [ISO 8601 Timestamps](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#timestamps) {#4-5-iso-8601-timestamps}

**Definitions**

1.  A Timestamp is defined as a Date/Time formatted according to ISO 8601

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00122 | A Timestamp MUST preserve precision to at least milliseconds (3 decimal points beyond seconds). The LRS accepts a statement with a valid timestamp which has more than 3 decimal points beyond seconds and when recalled it returns at least 3 decimals points beyond seconds. |
| XAPI-00123 | A Timestamp must conform to ISO 8601 Date format. An LRS rejects a statement with a Timestamp which doesn’t validate to ISO 8601 Extended or ISO 8601 Basic. |