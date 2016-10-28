## 2.3. [Statement Lifecycle](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#lifecycle) {#2-3-statement-lifecycle}

With no applicable conformance requirements in this section of the xAPI Specification, this section is intentionally blank.

#### 2.3.1. [Statement Immutability](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#statement-immutability-and-exceptions) {#2-3-1-statement-immutability}

With no applicable conformance requirements in this section of the xAPI Specification, this section is intentionally blank.

#### 2.3.2. [Voiding](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#voided) {#2-3-2-voiding}

**Definitions**

1.  A Voided Statement is defined as a Statement that is not a Voiding Statement and is the Target of a Voiding Statement within the LRS
2.  A Voiding Statement is defined as a Statement whose &quot;verb&quot; property&#039;s &quot;id&quot; property&#039;s IRI ending with &quot;voided&quot;
3.  A Voiding Statement&#039;s Target is defined as the Statement corresponding to the &quot;object&quot; properties &quot;id&quot; property&#039;s UUID

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00016 | A Voiding Statement cannot Target another Voiding Statement. LRS behavior this new VOIDING statement MAY be rejected. If the LRS accepts that statement, the violating VOIDING statement SHOULD be ignored. |
| XAPI-00017 | An LRS rejects a Voiding Statement with 400 Bad Request if the &quot;objectType&quot; field does not have a value of &quot;StatementRef&quot; |
| XAPI-00018 | An LRS MUST consider a Statement it contains voided if the Statement is not itself a voiding Statement and the LRS also contains a voiding Statement referring to the first Statement. Test: Void a statement and then send a GET for that statement which uses “statementId” instead of “voidedStatementId.” The statement should then not be returned in the GET request, which should return a 404\. |
| XAPI-00019 | A Voiding Statement is defined as a Statement whose &quot;verb&quot; property&#039;s &quot;id&quot; property&#039;s IRI ending with &quot;voided&quot; |
| XAPI-00020 | A Voiding Statement&#039;s &quot;objectType&quot; field has a value of &quot;StatementRef&quot; |