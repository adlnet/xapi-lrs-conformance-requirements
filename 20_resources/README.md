# 2.0. [Resources](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#datatransfer) {#2-0-resources}

**Definition**

1.  A POST request is defined as a &quot;pure&quot; POST, as opposed to a GET taking on the form of a POST

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00139 | An LRS has a Statement API with endpoint &quot;base IRI&quot;+&quot;/statements&quot; |
| XAPI-00140 | An LRS implements all of the Statement, State, Agent, and Activity Profile sub-APIs |
| XAPI-00141 | An LRS&#039;s returned array of ids from a successful GET request all refer to documents stored after the TimeStamp in the &quot;since&quot; parameter of the GET request if such a parameter was present (7.5.table3.row2) |