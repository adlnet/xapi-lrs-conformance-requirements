## 2.1. [Statement Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#stmtres) {#2-1-statement-resource}

### 

### [2.1.1 PUT Statements](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#211-put-statements) {#2-1-1-put-statements}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00142 | An LRS cannot modify a Statement in the event it receives a Statement with statementID equal to a Statement in the LRS already. To test: Send one statement with a particular statement ID. Send a second statement with the same statement ID but everything else different. Retrieve the statement before the second statement and after and both retrieved statements MUST match. |
| XAPI-00143 | An LRS&#039;s Statement API upon processing a valid PUT request successfully returns code 204 No Content |
| XAPI-00144 | An LRS&#039;s Statement API accepts PUT requests only if it contains a &quot;statementId&quot; parameter, returning 204 No Content |
| XAPI-00145 | An LRS&#039;s Statement API rejects a PUT request which does not have a &quot;statementId&quot; parameter, returning 400 Bad Request |

###  {#-0}

### [2.1.2 POST Statements](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#212-post-statements) {#2-1-2-post-statements}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00146 | An LRS&#039;s Statement API upon processing a successful POST request returns code 200 OK and all Statement UUIDs within the POST |
| XAPI-00147 | An LRS&#039;s Statement API accepts POST requests |
| XAPI-00148 | An LRS accepts a valid POST request containing a GET request returning 200 OK and the StatementResult Object. |

###  {#-1}

### [2.1.3 GET Statements](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#213-get-statements) {#2-1-3-get-statements}

**Definition**

1.  A GET request is defined as either a GET request or a POST request containing a GET request

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00149 | The LRS will NOT reject a GET request which returns an empty &quot;statements&quot; property. Send a GET request which will not return any results and check that a 200 Ok and an empty StatementResult Object is returned. |
| XAPI-00150 | An LRS&#039;s Statement API rejects a GET request with both &quot;voidedStatementId&quot; and anything other than &quot;attachments&quot; or &quot;format&quot; as parameters with error code 400 Bad Request. |
| XAPI-00151 | An LRS&#039;s Statement API rejects a GET request with both &quot;statementId&quot; and anything other than &quot;attachments&quot; or &quot;format&quot; as parameters with error code 400 Bad Request. |
| XAPI-00152 | An LRS&#039;s &quot;X-Experience-API-Consistent-Through&quot; header&#039;s value is not before (temporal) any of the &quot;stored&quot; values of any of the returned Statements. |
| XAPI-00153 | An LRS&#039;s Statement API upon processing a GET request, returns a header with name &quot;X-Experience-API-Consistent-Through&quot; regardless of the code returned. |
| XAPI-00154 | An LRS&#039;s Statement API upon processing a successful GET request with neither a &quot;statementId&quot; nor a &quot;voidedStatementId&quot; parameter, returns code 200 OK and a StatementResult Object. |
| XAPI-00155 | An LRS&#039;s Statement API upon processing a successful GET request with a &quot;voidedStatementId&quot; parameter, returns code 200 OK and a single Statement with the corresponding &quot;id&quot;. |
| XAPI-00156 | An LRS&#039;s Statement API upon processing a successful GET request with a &quot;statementId&quot; parameter, returns code 200 OK and a single Statement with the corresponding &quot;id&quot;. |
| XAPI-00157 | An LRS&#039;s Statement API can process a GET request with &quot;voidedStatementId&quot; as a parameter |
| XAPI-00158 | An LRS&#039;s Statement API can process a GET request with &quot;statementId&quot; as a parameter |
| XAPI-00159 | An LRS&#039;s Statement API accepts GET requests |
| XAPI-00160 | An LRS&#039;s &quot;X-Experience-API-Consistent-Through&quot; header is an ISO 8601 combined date and time |
| XAPI-00161 | An LRS&#039;s Statement API not return attachment data and only return application/json if the &quot;attachment&quot; parameter set to &quot;false&quot; |
| XAPI-00162 | An LRS&#039;s Statement API processes a successful GET request using a parameter (such as stored time) which includes a voided statement and unvoided statements targeting the voided statement. The API must return 200 Ok and the statement result object, containing statements which target a voided statement, but not the voided statement itself. |
| XAPI-00163 | An LRS&#039;s Statement API, upon processing a successful GET request, can only return a Voided Statement if that Statement is specified in the voidedStatementId parameter of that request |
| XAPI-00164 | The Statements within the &quot;statements&quot; property will correspond to the filtering criterion sent in with the GET request |
| XAPI-00165 | An LRS&#039;s Statement API, upon receiving a GET request, MUST have a &quot;Content-Type&quot; header. |
| XAPI-00166 | An LRS&#039;s Statement API can process a GET request with &quot;ascending&quot; as a parameter The Statement API MUST return 200 OK, StatementResult Object with results in ascending order of stored time if the ascending parameter is set to true. |
| XAPI-00167 | An LRS&#039;s Statement API can process a GET request with &quot;attachments&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object and use the multipart response format and include all attachments if the attachment parameter is set to true |
| XAPI-00168 | An LRS&#039;s Statement API can process a GET request with &quot;format&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with results in the requested format or in “exact” if the “format” parameter is absent. |
| XAPI-00169 | An LRS&#039;s Statement API can process a GET request with &quot;format&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with results in the requested format. If “canonical”, return Activity Objects and Verbs populated with the canonical definition of the Activity Objects and Display of the Verbs as determined by the LRS, returning only one language. |
| XAPI-00170 | An LRS&#039;s Statement API can process a GET request with &quot;format&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with results in the requested format. If “exact”, return Agent, Activity, Verb and Group Objects populated exactly as they were when the Statement was received. |
| XAPI-00171 | An LRS&#039;s Statement API can process a GET request with &quot;format&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with results in the requested format. If “ids”, only include identifiers for Agent, Activity, Verb, Group Objects, and members of Anonymous groups. |
| XAPI-00172 | If the &quot;Accept-Language&quot; header is present as part of the GET request to the Statement API and the &quot;format&quot; parameter is set to &quot;canonical&quot;, the LRS MUST apply this data to choose the matching language in the response. |
| XAPI-00173 | An LRS&#039;s Statement API can process a GET request with &quot;limit&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with only the number of results set by the integer in the limit parameter. If the limit parameter is not present, the limit is defaulted to 0 which returns all results up to the server limit. |
| XAPI-00174 | An LRS&#039;s Statement API can process a GET request with &quot;until&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object containing all statements which have a stored timestamp at or before the specified until parameter timestamp. |
| XAPI-00175 | An LRS&#039;s Statement API can process a GET request with &quot;since&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object containing all statements which have a stored timestamp after the since parameter timestamp in the query. |
| XAPI-00176 | An LRS&#039;s Statement API can process a GET request with &quot;related_agents&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with exact match agent results if the agent parameter is set with a valid Agent or Identified Group JSON Object unless the related_agents parameter is set to true. If set to true it MUST return 200 OK, StatementResult Object with agent matches in the Actor, Object, authority, instructor, team, or any of these properties in a contained SubStatement |
| XAPI-00177 | An LRS&#039;s Statement API can process a GET request with &quot;related_activities&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with exact match activity results if the activity parameter is set with a valid Verb IRI unless the related_activities parameter is set to true. If set to true it MUST return 200 OK, StatementResult Object with activity ID matches in the Statement Object, and Context Objects and SubStatement Objects. |
| XAPI-00178 | An LRS&#039;s Statement API can process a GET request with &quot;registration&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with exact match registration results if the registration parameter is set with a valid registration UUID |
| XAPI-00179 | An LRS&#039;s Statement API can process a GET request with &quot;activity&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with exact match activity results if the activity parameter is set with a valid activity IRI |
| XAPI-00180 | An LRS&#039;s Statement API can process a GET request with &quot;verb&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with exact match verb results if the verb parameter is set with a valid Verb IRI |
| XAPI-00181 | An LRS&#039;s Statement API can process a GET request with &quot;agent&quot; as a parameter. The Statement API MUST return 200 OK, StatementResult Object with exact match agent result if the agent parameter is set with a valid Agent IFI |