## 4.6. [ISO 8601 Durations](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#durations) {#4-6-iso-8601-durations}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00124 | A Duration MUST be expressed using the format for Duration in ISO 8601:2004(E) section 4.4.3.2\. The alternative format (in conformity with the format used for time points and described in ISO 8601:2004(E) section 4.4.3.3) MUST NOT be used. The LRS rejects with 400 a statement which includes the “duration” property and the value does not validate to ISO 8601:2004(E) section 4.4.3.2. |