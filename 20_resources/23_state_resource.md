## 2.3. [State Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#stateres) {#2-3-state-resource}

**Requirements**

| ID | Requirement |
| --- | --- |
| XAPI-00187 | An LRS&#039;s State API upon processing a successful DELETE request returns code 204 No Content |
| XAPI-00188 | An LRS&#039;s State API upon processing a successful GET request returns 200 Ok, State Document |
| XAPI-00189 | An LRS&#039;s State API upon processing a successful POST request returns code 204 No Content |
| XAPI-00190 | An LRS&#039;s State API upon processing a successful PUT request returns code 204 No Content |
| XAPI-00191 | An LRS&#039;s State API upon processing a successful DELETE request with a valid &quot;stateId&quot; as a parameter deletes the document satisfying the requirements of the DELETE and returns code 204 No Content NOTE: There is no requirement here that the LRS reacts to the &quot;since&quot; parameter in the case of a DELETE request with valid &quot;stateId&quot; - this is intentional |
| XAPI-00192 | An LRS&#039;s State API upon processing a successful GET request with a valid &quot;stateId&quot; as a parameter returns the document satisfying the requirements of the GET and code 200 OK NOTE: There is no requirement here that the LRS reacts to the &quot;since&quot; parameter in the case of a GET request with valid &quot;stateId&quot; - this is intentional |
| XAPI-00193 | An LRS&#039;s State API upon processing a successful GET request without &quot;stateId&quot; as a parameter returns an array of ids of state data documents satisfying the requirements of the GET and code 200 OK |
| XAPI-00194 | An LRS&#039;s State API upon processing a successful DELETE request without &quot;stateId&quot; as a parameter deletes documents satisfying the requirements of the DELETE and code 204 No Content |
| XAPI-00195 | An LRS&#039;s returned array of ids from a successful GET request all refer to documents stored after the TimeStamp in the &quot;since&quot; parameter of the GET request |
| XAPI-00196 | An LRS&#039;s State API rejects a DELETE request with &quot;agent&quot; as a parameter if it is not in JSON format with error code 400 Bad Request |
| XAPI-00197 | An LRS&#039;s State API rejects a GET request with &quot;agent&quot; as a parameter if it is not in JSON format with error code 400 Bad Request |
| XAPI-00198 | An LRS&#039;s State API rejects a POST request with &quot;agent&quot; as a parameter if it is not in JSON format with error code 400 Bad Request |
| XAPI-00199 | An LRS&#039;s State API rejects a PUT request with &quot;agent&quot; as a parameter if it is not in JSON format with error code 400 Bad Request |
| XAPI-00200 | An LRS&#039;s State API rejects a DELETE request with &quot;registration&quot; as a parameter if it is not a UUID with error code 400 Bad Request |
| XAPI-00201 | An LRS&#039;s State API rejects a GET request with &quot;registration&quot; as a parameter if it is not a UUID with error code 400 Bad Request |
| XAPI-00202 | An LRS&#039;s State API rejects a POST request with &quot;registration&quot; as a parameter if it is not a UUID with error code 400 Bad Request |
| XAPI-00203 | An LRS&#039;s State API rejects a PUT request with &quot;registration&quot; as a parameter if it is not a UUID with error code 400 Bad Request |
| XAPI-00204 | An LRS&#039;s State API rejects a GET request with &quot;since&quot; as a parameter if it is not a &quot;TimeStamp&quot;, with error code 400 Bad Request |
| XAPI-00205 | An LRS&#039;s State API rejects a DELETE request with &quot;since&quot; as a parameter if it is not a &quot;TimeStamp&quot;, with error code 400 Bad Request |
| XAPI-00206 | An LRS&#039;s State API rejects a PUT request without &quot;stateId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00207 | An LRS&#039;s State API rejects a DELETE request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00208 | An LRS&#039;s State API rejects a GET request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00209 | An LRS&#039;s State API rejects a POST request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00210 | An LRS&#039;s State API rejects a PUT request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00211 | An LRS&#039;s State API rejects a POST request without &quot;stateId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00212 | An LRS&#039;s State API rejects a DELETE request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00213 | An LRS&#039;s State API rejects a GET request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00214 | An LRS&#039;s State API rejects a POST request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00215 | An LRS&#039;s State API rejects a PUT request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00216 | An LRS&#039;s State API can process a DELETE request with &quot;stateId&quot; as a parameter |
| XAPI-00217 | An LRS&#039;s State API can process a GET request with &quot;stateId&quot; as a parameter |
| XAPI-00218 | An LRS&#039;s State API can process a PUT request with &quot;registration&quot; as a parameter |
| XAPI-00219 | An LRS&#039;s State API can process a DELETE request with &quot;registration&quot; as a parameter |
| XAPI-00220 | An LRS&#039;s State API can process a GET request with &quot;registration&quot; as a parameter |
| XAPI-00221 | An LRS&#039;s State API can process a GET request with &quot;since&quot; as a parameter. Returning 200 OK and all matching profiles after the date/time of the “since” parameter. |
| XAPI-00222 | The State API&#039;s returned array of ids from a successful GET request all refer to documents stored after the TimeStamp in the &quot;since&quot; parameter of the GET request if such a parameter was present |
| XAPI-00223 | An LRS&#039;s State API can process a DELETE request with &quot;since&quot; as a parameter |
| XAPI-00224 | An LRS&#039;s State API rejects a DELETE request with &quot;stateId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request |
| XAPI-00225 | An LRS&#039;s State API rejects a GET request with &quot;stateId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request |
| XAPI-00226 | An LRS&#039;s State API rejects a POST request with &quot;stateId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request |
| XAPI-00227 | An LRS&#039;s State API can process a POST request with &quot;registration&quot; as a parameter |
| XAPI-00228 | An LRS&#039;s State API rejects a PUT request with &quot;stateId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request |
| XAPI-00229 | An LRS&#039;s State API, rejects a POST request if the document is found and either document is not a valid JSON Object |
| XAPI-00230 | An LRS has a State API with endpoint &quot;base IRI&quot;+&quot;/activities/state&quot; |
| XAPI-00231 | An LRS will accept a POST request to the State API |
| XAPI-00232 | An LRS&#039;s State API, rejects a POST request if the document is found and either document&#039;s type is not &quot;application/json&quot; with error code 400 Bad Request |
| XAPI-00233 | An LRS&#039;s State API, upon receiving a POST request for a document not currently in the LRS, treats it as a PUT request and store a new document. Returning 204 No Content |
| XAPI-00234 | An LRS&#039;s State API performs a Document Merge if a profileId is found and both it and the document in the POST request have type &quot;application/json&quot;. If the merge is successful, the LRS MUST respond with HTTP status code 204 No Content. |
| XAPI-00235 | An LRS must reject with 400 Bad Request a POST request to the State API which contains name/value pairs with invalid JSON and the Content-Type header is &quot;application/json |