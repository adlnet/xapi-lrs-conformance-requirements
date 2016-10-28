## 2.6. [Agent Profile Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#agentprofres) {#2-6-agent-profile-resource}

**Requirements**

| ID | Requirement |
| --- | --- |
| XAPI-00255 | An LRS&#039;s Agent Profile API rejects a DELETE request with &quot;agent&quot; as a parameter if it is not an Agent Object with error code 400 Bad Request |
| XAPI-00256 | An LRS&#039;s Agent Profile API rejects a POST request with &quot;agent&quot; as a parameter if it is not an Agent Object with error code 400 Bad Request |
| XAPI-00257 | An LRS&#039;s Agent Profile API rejects a PUT request with &quot;agent&quot; as a parameter if it is not an Agent Object with error code 400 Bad Request |
| XAPI-00258 | An LRS&#039;s Agent Profile API rejects a GET request with &quot;agent&quot; as a parameter if it is not an Agent Object with error code 400 Bad Request |
| XAPI-00259 | The Agent Profile API MUST return 200 OK - Profile Content when a GET request is received with a valid agent JSON Object. |
| XAPI-00260 | An LRS&#039;s Agent Profile API rejects a GET request with &quot;since&quot; as a parameter if it is not a &quot;TimeStamp&quot;, with error code 400 Bad Request |
| XAPI-00261 | An LRS&#039;s Agent Profile API rejects a GET request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00262 | An LRS&#039;s Agent Profile API rejects a DELETE request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00263 | An LRS&#039;s Agent Profile API rejects a POST request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00264 | An LRS&#039;s Agent Profile API rejects a PUT request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00265 | An LRS&#039;s Agent Profile API rejects a DELETE request without &quot;profileId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00266 | An LRS&#039;s Agent Profile API rejects a POST request without &quot;profileId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00267 | An LRS&#039;s Agent Profile API rejects a PUT request without &quot;profileId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00268 | An LRS&#039;s Agent Profile API can process a GET request with &quot;since&quot; as a parameter. Returning 200 OK and all matching profiles after the date/time of the “since” parameter. |
| XAPI-00269 | An LRS&#039;s Agent Profile API upon processing a successful GET request with a valid Agent Object and valid &quot;profileId&quot; as a parameter returns the document satisfying the requirements of the GET and code 200 OK |
| XAPI-00270 | An LRS&#039;s Agent Profile API upon processing a successful GET request with a valid Agent Object and without &quot;profileId&quot; as a parameter returns an array of ids of agent profile documents satisfying the requirements of the GET and code 200 OK |
| XAPI-00271 | An LRS&#039;s Agent Profile API upon processing a successful DELETE request deletes the associated profile and returns code 204 No Content |
| XAPI-00272 | An LRS&#039;s Agent Profile API upon processing a successful POST request returns code 204 No Content |
| XAPI-00273 | An LRS&#039;s Agent Profile API upon processing a successful PUT request returns code 204 No Content |
| XAPI-00274 | An LRS&#039;s Agent Profile API accepts valid GET requests with code 200 OK, Profile document |
| XAPI-00275 | The Agent Profile API&#039;s returned array of ids from a successful GET request all refer to documents stored after the TimeStamp in the &quot;since&quot; parameter of the GET request if such a parameter was present |
| XAPI-00276 | An LRS&#039;s Agent Profile API rejects a POST request with &quot;profileId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request |
| XAPI-00277 | An LRS&#039;s Agent Profile API rejects a PUT request with &quot;profileId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request |
| XAPI-00278 | An LRS&#039;s Agent Profile API, rejects a POST request if the document is found and either document&#039;s type is not &quot;application/json&quot; with error code 400 Bad Request |
| XAPI-00279 | An LRS&#039;s Agent Profile API performs a Document Merge if a profileId is found and both it and the document in the POST request have type &quot;application/json&quot; If the merge is successful, the LRS MUST respond with HTTP status code 204 No Content. |
| XAPI-00280 | An LRS&#039;s Agent Profile API, upon receiving a POST request for a document not currently in the LRS, treats it as a PUT request and store a new document.Returning 204 No Content |
| XAPI-00281 | An LRS&#039;s Agent Profile API, rejects a POST request if the document is found and either document is not a valid JSON Object |
| XAPI-00282 | An LRS has an Agent Profile API with endpoint &quot;base IRI&quot;+&quot;/agents/profile&quot; |
| XAPI-00283 | An LRS will accept a POST request to the Agent Profile API |
| XAPI-00284 | An LRS must reject, with 400 Bad Request, a POST request to the Agent Profile API which contains name/value pairs with invalid JSON and the Content-Type header is &quot;application/json |