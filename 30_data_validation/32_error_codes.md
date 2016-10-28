## 3.2. [Error Codes](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#errorcodes) {#3-2-error-codes}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00323 | An LRS can only reject Statements using the error codes in this specification |
| XAPI-00324 | An LRS rejects with error code 400 Bad Request any request to an API which uses a parameter not recognized by the LRS |
| XAPI-00325 | An LRS rejects with error code 400 Bad Request any request to an API which uses a parameter with differing case |
| XAPI-00326 | An LRS rejects with a 400 Bad Request any batch of Statements in which one or more Statements is rejected and if necessary, restores the LRS to the state in which it was before the batch began processing. The response may identify the first statementId which failed. |
| XAPI-00327 | An LRS rejects a Statement of insufficient permissions (credentials are valid, but not adequate) with error code 403 Forbidden |
| XAPI-00328 | An LRS rejects a Statement due to size if the Statement exceeds the size limit the LRS is configured to with error code 413 Request Entity Too Large. Suggestion: test increasingly larger statements to identify capacity of the upper limit - 1MB, 5MB, 10MB, 20MB until a 413 is returned. |
| XAPI-00329 | An LRS rejects a Statement due to network/server issues with an error code of 500 Internal Server Error |