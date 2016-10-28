## 3.1. [Concurrency](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#concurrency) {#3-1-concurrency}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00322 | An LRS must support HTTP/1.1 entity tags (ETags) to implement optimistic concurrency control when handling APIs where PUT may overwrite existing data (State, Agent Profile, and Activity Profile) |